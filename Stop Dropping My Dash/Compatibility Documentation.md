# Stop Dropping My Dash − Compatibility Documentation
This document will note some details that may be useful if you want to build compatibility between your mod and **Stop Dropping My Dash**.

In all cases your mod should be loaded ABOVE **Stop Dropping My Dash** for compatibility to work as expected.

I have included a "proof of concept" example mod for compatibility with **Amy Galore**. I do not match compatibility 1:1 with **Amy Galore**'s implementation of these objects and have taken my own little spin on how Amy should interact with these objects and there is even a configuration option! 
## The Objects and Functions
This mod replaces multiple functions of the base Sonic 3 A.I.R.

I would advise that if you have some custom logic in your own mod when interacting with these objects already, then I would suggest having checking the preprocessing varable ``SDMD_ACTIVE`` before loading those functions. Such a check might look like this:

```
#if !SDMD_ACTIVE
function void functionOne()
{
  // Code here
}

function void functionTwo()
{
  // Code here
}
#endif
```

Such a check will load your code only if **Stop Dropping My Dash** is not loaded.

Obviously, if you have some extra feature that your character can do that you will *need* to handle then you should not revert to the base function if the conditions of your function are met.

You should be able to do this by checking if **Stop Dropping My Dash** is loaded and the special condition hasn't been met, then falling back to the base function should work. Such code may look like:

```
function void functionName()
{
    if (Mods.isModActive("Stop Dropping My Dash") && !ConditionMet)
    {
        base.functionName()
        return
    }

    // Rest of your code here
}
```

So you know what functions to look out for I have provided full list of the game objects, addresses and Functions that have been changed by **Stop Dropping My Dash** below.

|Object|Address Hook|Function|
|---|---|---|
|Rocks|``0x01faf2``|``Rocks.Update()``|
|Rocks|``0x01fbae``|``fn01fbae()``|
|Rocks|``0x01fba8``|``fn01fba8()``|
|Rocks|``0x020056``|``fn020056()``|
|Cork Floor|``0x02a502``|``fn02a502()``|
|Cork Floor|``0x02a588``|``fn02a58e()``|
|Cork Floor|``0x02a588``|``fn02a588()``|
|CNZ Balloons|``0x0317ae``|``fn0317ae()``|
|CNZ Circle Bumpers|``0x032f56``|``fn032f56()``|
|ICZ Ice Block|``0x08b384``|``fn08b384()``|
|ICZ Ice Block|``0x08b3aa``|``fn08b3aa()``
|SOZ Rocks|``0x04172e``|``fn04172e()``|
|SOZ Rocks|``0x0417a6``|``fn0417a6()``|

In addition, a few other functions were altered that are not specific:
|Method|Address Hook| Function
|---|---|---|
|Collision Check|``0x01dc56``|``fn01dc56()``
|Character Jump Moves||``Character.updateJumpMoves()``

>**PLEASE NOTE:** Please note that I have moved the Collision Check (``0x01dc56``) for the ICZ Ice Block out of ``0x08b384`` and into ``0x08b3aa``. So you may need to account for that if you have super specific character logic for the ICZ Ice Block.

This mod also updated the method ``P2Balloons()`` from **Origins Parity Galore** and ``SuperThenHyperfunc()`` from **Characters Go Supper Then Hyper** to ensure compatible functionality.

## The Helper Functions
To ensure compatibility with custom characters, I have added some helper functions that you mod can override to allow **Stop Dropping My Dash** to know how your custom character should interact with the objects in this mod.

In all cases, if your characters condition was not met, please remember to ``return`` the base function.

### Function 1: ``SDMD.canBounce(u8 state.in)``
This function will return a ``bool`` and checks if the Player 1 character can break the object and bounce off of it.

It takes a state as the input, but there is no guarantee what any of the address registers are when the function starts, so please remember to set them if needed.

By default, this function checks for Sonic's Drop Dash state and **Extra Slot Amy**'s hammer bounce.

### Function 2: ``SDMD.canSmash(u8 state.in)``
This function will return a ``bool`` and checks if the Player 1 character can break the object and should continue straight through.

Again, it takes a state as the input, but there is no guarantee what any of the address registers are when the function starts, so please remember to set them if needed.

By default, this function checks for **Extra Slot Mighty**'s hammer drop, **Extra Slot Amy**'s hammer slam and **Extra Slot 3D in 2D Shadow**'s drop down.

### Function 3: ``SDMD.restoreSmash()``
This function is a ``void`` return and is here to restore the specific details of the state that caused ``SDMD.canSmash(u8)`` to return true.

This is needed because the collision with the object will most likely remove this state from your character and we need to restore it. Or at least, that has been the case for existing Extra Slot characters I normally use.

By default, this function restores the required values for **Extra Slot Mighty**'s hammer drop, **Extra Slot Amy**'s hammer slam and **Extra Slot 3D in 2D Shadow**'s drop down to continue.

### Function 4: ``SDMD.allowUpwardsMotion()``
This function will return a ``bool`` and is here to check if the extra upwards motion provided by CNZ Balloons or Bumpers should be removed due to a double jump move's execution.

This function should return ``true`` unless your characters move would normally push them down, such as **Extra Slot Mighty**'s hammer drop, that is checked for by default.

### Function 5: ``SDMD.destroyObjectExternally()``
This function will return a ``bool`` and is here to check if Rocks, ICZ Ice Blocks and SOZ Blocks have been destroyed by some external reason distinct from landing on top of them.

If the value returned is ``true`` then the objects will be destroyed regardless of the interaction. This is called right after the collision check function ``fn01dc56()``, so you are able to do any collision checks if required.

This function will return ``false`` by default and was created for some compatibility with **Amy Galore**'s Idle Hammer swing that destroys these objects from the side.

# Compatibility Documentation
This document will note some details that may be useful if you want to build compatibility between your mod and **Break That Pipe!**

In all cases your mod should be loaded ABOVE **Break That Pipe!** for compatibility to work as expected.

I have included a "proof of concept" example mod for compatibility with **Amy Galore**. This compatibility is not actually required if you load **Break That Pipe!** below **Amy Galore** as they already handle this object within their own mod.
## The Objects and Functions
This mod replaces the ``fn027424()`` function at address hook ``0x027424`` of the base Sonic 3 A.I.R.

## The Helper Functions
To ensure compatibility with custom characters, I have added some helper functions that you mod can override to allow **Break That Pipe!** to know how your custom character should interact with the objects in this mod.

### Function 1: ``BTP.canBreak(u8 state.in)``
This function will return a ``bool`` and checks if the Player 1 character can break the object.

It takes a state as the input and the address at ``A1`` should relate to either Player 1 (``0xffffb000``) or Player 2 (``0xffffb04a``).

By default, this function checks for Sonic's Drop Dash state and **Extra Slot Amy**'s hammer bounce and **Extra Slot 3D in 2D Shadow**'s boost.

### Function 2: ``BTP.destroyObjectExternally()``
This function will return a ``bool`` and is here to check if the pipe has been destroyed by some external reason distinct from player collision interactions.

If the value returned is ``true`` then the objects will be destroyed regardless of the interaction. This is called right after the collision check function ``fn01dc56()``, so you are able to do any collision checks if required.

This function will return ``false`` by default and was created while testing a proof of concept **Amy Galore** compatibility mod.

# Paper's HUD Additions − Compatibility Documentation
This document will note some details that may be useful if you want to build compatibility between your mod and **Paper's HUD Additions**.

In all cases your mod should be loaded ABOVE **Paper's HUD Additions** for compatibility to work as expected.

I have included a "proof of concept" mod that turns the transform button into a revert button if the Super Cancel setting in Sonic 3 A.I.R. is on.
## Asset Compatibility Requirements
To ensure that you custom character has compatibility with the new Lives Icon rendering mode, then you need to ensure that both the functions ``getCharacterSpriteKey(u8 character)`` and/or ``getCharacterSpriteKey(u8 character, bool isSuperActive)`` are return the correct character string for your character. The isSuperActive flag is used to retrieve the character detail regardless of super form for the character name art and related to the variables in the table below.

|Variable|Function|
|---|---|
|``characterSprite``|``getCharacterSpriteKey(u8 character)``|
|``characterName``| ``getCharacterSpriteKey(u8 character, false)``

For each character life icon, you are provided to provide assets that match the below strings.

|%s|Texture String|Purpose
|---|---|---|
|``characterSprite``|``"%s_lives_icon"``|Character Face Sprite (BMP Preferred)
|``characterSprite``|``"%s_lives_icon_ring_s3"``|Border of the character face in Sonic 3's HUD word style 
|``characterSprite``|``"%s_lives_icon_ring_haru"``|Border of the character face in Haru's Forever-esc HUD word style 
|``characterSprite``|``"%s_lives_icon_border_s3"``|Border of the character face in Sonic 3's HUD number style
|``characterSprite``|``"%s_lives_icon_border_haru"``|Border of the character face in Haru's Forever-esc HUD number style
|``characterName``|``"%s_lives_text_s3"``|Character name for the lives text in Sonic 3's HUD style, includes the ×.
|``characterName``|``"%s_lives_text_haru"``|Character name for the lives text in Haru's Forever-esc HUD style, includes the ×.

## Compatibility with rendering the HUD
This mod replaces the ``RenderHUD()`` function of the base Sonic 3 A.I.R. and as such, other mods that alter this function will possibly conflict.

To help with this I have moved the logic to render the Transform Button and Lives detail into their own functions ``PHUD.RenderTransformButton()`` and ``PHUD.RenderLives(u16 px, u16 py, u16 renderQueue)``, respectively. These will be explained in greater detail further down the document.

You can check the preprocessing variable ``PHUD_ACTIVE`` that is added by this mod before loading those functions in locations where you want them to be seen. For example, if your custom UI section needs to render the lives icon, you can use something like the below code chunk.

```
#if PHUD_ACTIVE
if (!PHUD.RenderLives(px, py, renderQueue))
#endif
{
  // Your fallback lives rendering code here.
}
```

Such a check will load **Paper's HUD Additions**' Lives HUD if it is earlier in the load order, and fall back to your own rendering if it fails for some reason or is not loaded.

Similar can be done to load the Transform Button if required.

In addition to this, there are some additional functions to 

## The Helper Functions
To ensure compatibility with custom characters, I have added some helper functions that you mod can override to allow **Paper's HUD Additions** to adjust the way that certain aspects of this mod work for your custom character.

In all cases, if your characters condition was not met, please remember to ``return`` the base function.

### Function 1: ``PHUD.RenderTransformButton()``
This function is a ``void`` function that simple renders the transform button on the HUD.

You generally should not need to interact with this method, but may want to call it if you are doing a total HUD replacement and are checking the preprocessing variable ``PHUD_ACTIVE``.

### Function 2: ``PHUD.RenderLives(u16 px, u16 py, u16 renderQueue)``
This function will attempt to render the lives icon and will return a ``bool``. If it fails to render due to being unable to find the base character icon then it will return ``false``. In the base mod this causes the base ``RenderHUD()`` function to run.

Again, you generally should not need to interact with this method, but may want to call it if you are doing a total HUD replacement and are checking the preprocessing variable ``PHUD_ACTIVE``.

### Function 3: ``PHUD.CanTransform()``
This function returns a ``bool``. It is the conditional check that the current character meets the conditions to transform.

If you have alternate super form conditions for your character, such as more rings required or a different set of emeralds then you can check for this here.

### Function 4: ``PHUD.ButtonIsValid()``
This function will return a ``bool`` and is here to check if pressing the transform button will actually cause the character to transform in their current state.

You can check for something specific to your character here if need be.

### Function 5: ``PHUD.GetTransformIcon(bool style)``
This function will return a ``u64`` that is used for the sprite string of the transform button's icon.

The ``style`` that is passed to this function will be ``true`` if a border is in use and ``false`` if no border is in use. 

### Function 6: ``PHUD.MobileLivesOffset()``
This function will return a ``u16`` and is here to provide an additional offset for your character's mobile lives position.

This is used in the base mod because I used the term "KNUCKLES" instead of "K·T·E" and needed to push the lives icon in a little more in the mobile view to keep the name on screen.
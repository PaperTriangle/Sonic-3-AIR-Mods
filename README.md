# Sonic-3-AIR-Mods
A collection of PaperTriangle's Sonic 3 A.I.R. Mods both in progress and released.

## Alternate LBZ2 Cutscene
Converts the LBZ2 Ending scene after beating Big Arm to me a bit more like Origins.

I know this is not _exactly_ like Origins, but this is as close as I intend to get.

I would recommend using this mod along with **LBZ Eggman Fleeing**, **Origins Parity Galore** and **Better Big Arm Fade**! You will need to load this mod over them.

## Battery Powered Intro
Simple mod that adds in two intro styles for FBZ! I Would honestly not recommend using it as there are better options out there.

## Better Big Arm Fade
This mod makes the fade effect of the background at the start of the Big Arm fight use the Sonic 3 A.I.R. methods to blend the background palette colours. This allows the fade to work with custom palettes!

There is a setting to decide how smooth the blend is.

**PLEASE NOTE:** If you use **Ambient Mod** for the rain in the Big Arm fight, please place it above this mod or the rain will not end correctly!

## Break That Pipe!
This mod simply makes the LBZ2 pipes breakable by Knuckles and Super Sonic.

## Broken Badniks
Adds broken bits of certain badniks as particles that fall when the badnik dies. There are also has some adjustments for mini-bosses.

## Classic Hyper Trails
Allows some customisation of the Hyper trail effect to get closer to the Mega Drive original.

**PLEASE NOTE:** This mod requires **No Transparency** to function and should be loaded above any extra character mods.

## Colour Clamp
Clamps the colours in the game to a maximum brightness of 252 in most places. Also has options to be more like the Retro Engine games or old PC port.

Code was adapted from nabbup's **Basic Overlay Mod**.

## Data Select Options
Adds some options to the data select like adding semi-transparent shadows, removing the emerald glint and shifting everything to the left a bit for less wasted screen space.

Also has an option to remove the lives and continues detail, shifting the player icons down. This has some hacky Extra Slot support that might not work for all characters...

## Don't Stop My Glide
Allows Knuckles' glide to land on dynamic objects and prevents the glide from stopping while gliding through certain objects.

Also adds in a couple of extra frames to Knuckles from Origins and some other options like Hyper Stars for Hyper Knuckles.

## ESU Origins Resolution Tweaks
Some tweaks for ESU characters so they work with the Origins Resolution mod... Mostly around intro cutscenes. Also replaces the act clear icons with a PNG version of the UI symbol to prevent water palettes interacting with the HUD.

## Extended Palette For Giant Ring
Makes the Giant Ring operate using an extended palette line. Preventing the Super Rings from messing with stage / HUD palettes.

## Flying Hold Frame Fix
Makes the animation while holding on to Tails less jumpy. Should be placed below other sprite mods. Should work with ESU if placed below it.

## Gotta Go Fast!
A mod that adds in a Fast Run to Sonic and Knuckles. Can also override some ESU characters for consistency.

**PLEASE NOTE:** This mod is for my own personal use and it includes random sprites I have found. I have tried to provide a credit to the original creators for the ones I remember... But fuck idk where those Sonic ones came from...

## Haru Style Monitors Plus HUD
Adjusts the HUD elements of the Hyper Ring to better match the Haru's Forever-esc style.

## HCZ & ICZ Alternate Title Cards
Simple mod to put a space in "HYDROCITY" and "ICECAP" title cards, making them "HYDRO CITY" and "ICE CAP", respectively.

**PLEASE NOTE:** This requires Veenee's **Title Card Elements and Results Screen Sprites** mod to work. Also comes with a version in the style of Trimint123's **Zone Japanese Text** mod.

## Hydrocity Shake
Adjusts some of the animations for the player characters in HCZ to be more like Origins and fixes the frozen foreground tiles. Also fixes a minor object layout issue in HCZ1.

## Hyper Drop Dash
Makes Hyper Sonic have a Drop Dash function simmer to the **Hyper Mania** mod for Sonic Mania.

## Imma Let You Finish
Forces the characters to stop fidgeting and let the act end.

## Keep Rollin'
Makes characters keep rolling when passing from dynamic object to ground object.

**PLEASE NOTE:** This mod is pretty poorly coded and could be much more efficient...

## Moar Transparency
Adds transparency effects to more objects in the game. The effects can be *incredibly subtle* at some points and will bypass tranparency removal from **Moar Transparency**.

There are also some options in here to make the teleporters within the game more consistent across the zones.

## No Transparency
Remove the transparency effects from Sonic 3 AIR. This can be used with **Moar Transparency** to fine tune exactly what you want to be transparent.

**PLEASE NOTE:** This mod will not remove any transparency baked into a PNG file or render effects applied to a `SpriteHandle`.

## Paper's HUD Additions
Adds a new Sonic CD inspired life icon and a Transform button. Should work with regular and mobile views.

There is also an option to clone the player palette to an extended palette line, allow the lives icon to render above water super palette rotations while below water.

Hud Elements have compatibility with **Haru's Forever-esque HUD**. Lives icon has compatibility with **Plush's Ariff Tails**, **Extra Sloy Mighty, Ray & Amy** and **Extra Slot 3D in 2D Shadow**. The transform button has compatibility with **Characters Go Super Then Hyper** and **Easy Super**.

## Rotate
Makes player rotation worse... Made this as a test— I do not recommend using...

## Static Monitors Plus Hyper Rings
Places Hyper Ring power ups in zones at static locations. Most of the time this overrides existing power ups, but sometimes it adds new monitors. I created this because I wanted to use the Hyper Ring power up, but I don't like randomisers.

**PLEASE NOTE:** This mod hooks into the LevelObjectTableBuilder.addObject() function, so it will not work if you are using any mods to alter zone objects. I suggest deleting the rawdata related files for FBZ object pos from Misc. Fixes & Tweaks if you use both mods.

## Stop Dropping My Dash
Allows Sonic to hold a Drop Dash while bouncing off of more objects. Also allows characters to perform their double jump moves after interacting with these objects.

Has some compatibility with **ES Mighty**, **ES Amy** and **ES 3D2D Shadow**.

## Super Flicky Fix
Makes the Super Flickies render using Sonic's player palette line. Meaning game objects should not flash yellow.

Has some other options like Super/Hyper Stars for Super/Hyper Tails. Also has some compatibility with **Classic Hyper Trails** to make the OG Super Tails more "Super".

## Sweep Up That Dust
Removes the dust from the Spindash while the character is in the air and starts it again once they hit the ground. Also has an option for some more detailed spindash dust sprites.

## Time Consistent Adventure
This mod adjusts the palettes and some stage art for many zones to provide a more consistent passage of time with the Sonic & Tails and the Knuckles adventures.

An option has been added to run this using the released zone order, however this does disable many features of the mod.

**PLEASE NOTE:** The GitHub version of this mod comes with the related zone order code from **Useott's Original Zone Order** baked into the mod.

## Underwater Super/Hyper Palettes
Adds an underwater palette for Hyper Sonic, underwater palette options for Tails and Knuckles, and also has some options to make the flash less white to align with some of the ESU characters.

## Where's Robo
Updates LevelObjectTableBuilder.buildObjects_SSZ1() to ensure that the first Egg Robo badnik loads properly in 16:9 if using Sonic 3 A.I.R. layouts.
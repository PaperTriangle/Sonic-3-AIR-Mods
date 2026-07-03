# Sonic-3-AIR-Mods
A collection of PaperTriangle's Sonic 3 A.I.R. Mods both in progress and released.

**PLEASE NOTE:** I will only build compatibility with mods that I actually use on a regular basis. For most mods where compatibility would be required I have added functions in my mods so other modders can build compatibility into their own mods, or as seperate mods. Please do not feel offended if I reject a request for compatibility, but I just do not want to have to keep up a high level of maintenance when other mods update and change.

## Absolute Cinema
Prevents pausing during cutscenes, removes the HUD more often during cutscenes & can also prevent cutscene skipping.

## Alternate LBZ2 Cutscene
Converts the LBZ2 Ending scene after beating Big Arm to me a bit more like Origins.

I know this is not _exactly_ like Origins, but this is as close as I intend to get.

I would recommend using this mod along with **LBZ Eggman Fleeing**, **Origins Parity Galore**, **Origins Screen Resolution** and **Smoother Skies**! You will need to load this mod over them.

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

## Dash 'n' Dust
Makes Hyper Sonic have a Drop Dash function like the **Hyper Mania** mod for Sonic Mania and removes the dust from the Spindash while the character is in the air and starts it again once they hit the ground.

Also has options for dropdash animations, dust, screenclear while super and to add slightly more detailed dust sprites. Has compatibility with MF&T's Mania Dropdash sound override.

## Data Select Options
Adds some options to the data select like adding semi-transparent shadows, removing the emerald glint and shifting everything to the left a bit for less wasted screen space.

Also has an option to remove the lives and continues detail, shifting the player icons down. This has some hacky Extra Slot support that might not work for all characters...

## Don't Stop My Glide
Allows Knuckles' glide to land on dynamic objects and prevents the glide from stopping while gliding through certain objects.

Also adds in a couple of extra frames to Knuckles from Origins and some other options like Hyper Stars for Hyper Knuckles.

## Emulated Drowning Fix
As mentioned in **[this YouTube video](https://www.youtube.com/watch?v=ReSQMww1JZI)**, there is an issue with the drowning music in Sonic 3 where a certain channel does not play.

The video included Game Genie codes for a simple fix. I have simply just converted this into a rawdata mod that Sonic 3 A.I.R. will use to patch the rom so the track will emulate as originally intended.

## ESU Origins Resolution Tweaks
Some tweaks for ESU characters so they work with the **Origins Screen Resolution** mod... Mostly around intro cutscenes. Also replaces the act clear icons with a PNG version of the UI symbol to prevent water palettes interacting with the HUD.

## Extended Palette For Giant Ring
Makes the Giant Ring operate using an extended palette line. Preventing the Super Rings from messing with stage / HUD palettes.

## Extra Slot Mighty & Ray
Adds a partnered Mighty & Ray as Slot 4. This requires **ES Mighty** and **ES Ray** to work.

**PLEASE NOTE:** This mod is in an experimental and untested state!

## Fixed Fire colours
Renders the flame effects from AIZ2 on extended palette lines, fixs a small issue where the palettes are messed up for a few frames during the "Fire Wall" transition in Act 1! Also changes the new AIR logic to just prevent rendering the objects while underwater instead of unloading them, restoring that one flame in the draining sequence.

## Flying Hold Frame Fix
Makes the animation while holding on to Tails less jumpy. Should be placed below other sprite mods. Should work with ESU if placed below it.

## Frame Perfect Insta Shield
Lets you do the frame perfect insta shield jump off spikes thing.

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

## Imma Let You Finish
Forces the characters to stop fidgeting and let the act end.

## Keep Rollin'
Makes characters keep rolling when passing from dynamic object to ground object.

**PLEASE NOTE:** This mod is pretty poorly coded and could be much more efficient...

## Magnetic Attraction
Makes the electromagnets in FBZ attract Player 1 while they have the Lightning Shield.

## Moar Transparency
Adds transparency effects to more objects in the game. The effects can be *incredibly subtle* at some points and will bypass tranparency removal from **Moar Transparency**.

There are also some options in here to make the teleporters within the game more consistent across the zones.

## No Extra Invuln
Removes the extra second of invulnerability after being invincible... I wish this was a setting...

## No Transparency
Remove the transparency effects from Sonic 3 AIR. This can be used with **Moar Transparency** to fine tune exactly what you want to be transparent.

**PLEASE NOTE:** This mod will not remove any transparency baked into a PNG file or render effects applied to a `SpriteHandle`.

## Origins Resolution Title Screen
Updates the titlescreen to run in an Origins Resolution. Also includes a few other options.

If you have enabled the bypass A.I.R. Menu option, holding Y and BACK while pressing start will take you to the A.I.R. Menu.

**PLEASE NOTE:** The old school codes option will not work if you use the Sonic 3 A.I.R. main menu. This has been designed to use with mods like **Data Select Options** and **Paper's Pause**.

## Paper's HUD Additions
Adds a new Sonic CD inspired life icon and a Transform button. Should work with regular and mobile views.

There is also an option to clone the player palette to an extended palette line, allow the lives icon to render above water super palette rotations while below water.

Hud Elements have compatibility with **Haru's Forever-esque HUD**. Lives icon has compatibility with **Plush's Ariff Tails**, **Extra Sloy Mighty, Ray & Amy** and **Extra Slot 3D in 2D Shadow**. The transform button has compatibility with **Characters Go Super Then Hyper** and **Easy Super**.

## Paper's Pause
Adds a new pause menu that is how I may have imagined it if the game was re-released in the '90s.

## Smoother Cycles
Makes some stage palette cycles a smit smoother. This is mostly for cycles that take longer than 8 frames noormally, such as Lava, LRZ Crystals, those ICZ Green Crystals and the DEZ Orange thingies.

**PLEASE NOTE:** Recommended to turn off the **Misc. Fixes and Tweaks** settings for LRZ Glowing Crystals and restoring the cooled palette after the boss as this mod does the same thing and if both are enabled it acts funky.

## Smoother Skies
Makes the fades of sky palettes smoother during the MGZ to CNZ transition, the ICZ post Big Icedus sky fade and the Big Arm intro and outro fade.

This mod look directly at palette locations in the ROM and blends between them. This means it ***should*** work with custom rawdata palettes. Details on each specific palette address are located in a comment within the lemonscript file.

## Static Monitors Plus Hyper Rings
Places Hyper Ring power ups in zones at static locations. Most of the time this overrides existing power ups, but sometimes it adds new monitors. I created this because I wanted to use the Hyper Ring power up, but I don't like randomisers.

**PLEASE NOTE:** This mod hooks into the LevelObjectTableBuilder.addObject() function, so it will not work if you are using any mods to alter zone objects. I suggest deleting the rawdata related files for FBZ object pos from Misc. Fixes & Tweaks if you use both mods.

## Stop Dropping My Dash
Allows Sonic to hold a Drop Dash while bouncing off of more objects. Also allows characters to perform their double jump moves after interacting with these objects.

Has some compatibility with **ES Mighty**, **ES Amy** and **ES 3D2D Shadow**.

## Time Consistent Adventure
This mod adjusts the palettes and some stage art for many zones to provide a more consistent passage of time with the Sonic & Tails and the Knuckles adventures.

Thanks to Useott this mod also includes the logic to run it as either the originally intended zone order or the as released zone order!

**PLEASE NOTE:** If you use the "as released"  order this does disable many features of the mod.

## Triple Trouble 16-Bit Sounds
This mods adds sounds from Triple Trouble 16-Bit for Monitors and some DEZ2 objects.

## Tweakin' Tails
Started as a mod that makes the Super Flickies render using Sonic's player palette line. Meaning game objects should not flash yellow.

Has since been expanded with more options for Tails like Super/Hyper Stars for Super/Hyper Tails, Super Tails breaking walls, faster flight ascention while Super/Hyper & Tails' tail animation tweaks for looking up and the victory pose.

## Underwater Super/Hyper Palettes
Adds an underwater palette for Hyper Sonic, underwater palette options for Tails and Knuckles, and also has some options to make the flash less white to align with some of the ESU characters.

## Where's Robo
Updates LevelObjectTableBuilder.buildObjects_SSZ1() to ensure that the first Egg Robo badnik loads properly in 16:9 if using Sonic 3 A.I.R. layouts.
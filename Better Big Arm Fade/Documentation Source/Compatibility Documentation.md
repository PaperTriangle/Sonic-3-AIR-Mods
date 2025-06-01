# Better Big Arm Fade − Compatibility Documentation
This document will note some details that may be useful if you want to build compatibility between your mod and **Better Big Arm Fade**

In all cases your mod should be loaded above **Better Big Arm Fade** for compatibility to work as expected.

I have included a "proof of concept" example mod to demonstrate compatibility. This mod can be loaded without **Better Big Arm Fade** to demonstrate how the preprocessing variable works.
## The Replaced Functions
This mod replaces the  functions ``fn072e30()`` & ``fn07305a()`` at address hooks ``0x072e30`` and ``0x07305a``, respectively.

if your mod already replaces these methods, you can use a check for the preprocessing variable ``BBAF_ACTIVE`` to ensure the compiler does not include your methods if **Better Big Arm Fade** is loaded. This would look similar to the following:

```
#if !BBAF_ACTIVE

//# address-hook(0x072e30)
function void fn072e30()
{
  // Your code here.
}

//# address-hook(0x07305a)
function void fn07305a()
{
  // Your code here.
}

#endif
```

## The Helper Function
To add compatibility for a custom Big Arm sky palette the function ``BBAF.BigArmSky(u8 index)`` has been added. This will return a ``u16`` value that will be used for the palette line. The possible values for ``index`` are 0, 1, 2 & 3.

I would recomment immplementing this in your own mod similar to the below example:

```
constant array<u16> CUSTOM_SKY = {0x0448, 0x0226, 0x0004, 0x0002}

function u16 BBAF.BigArmSky(u8 index)
{
	return (index < 4) ? CUSTOM_SKY[index] : 0x00
}
```
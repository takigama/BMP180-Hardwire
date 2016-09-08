Sparkfun BMP180 Library Port To WireBase
========================================

Needed a version of this that uses hardwire
and that can choose easily betwen the two i2c
busses that are available. Using wirebase
makes it fairly agnosttic

All that changes is where you used to go:

> &#35;include &lt;SFE_BMP180.h&gt;

> &#35;include &lt;Wire.h&gt;
>
> SFE_BMP180 pressure;


You now go 
> &#35;include &lt;SFE_BMP180_hw.h&gt;
> 
> HardWire HWire(1, I2C_FAST_MODE);

> SFE_BMP180_hw pressure(&HWire);

If you want to use bus 2, you just go:

> &#35;include &lt;SFE_BMP180_hw.h&gt;
> 
> HardWire HWire(2, I2C_FAST_MODE);

> SFE_BMP180_hw pressure(&HWire);

Simples! Thanks Sparkfun for the excelent library

Love, Takigama (one day i'll clean up the obvious problems with my readme.md)

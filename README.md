Sparkfun BMP180 Library Port To Hardwire
========================================

Needed a version of this that uses hardwire
and that can choose with i2c bus to use

Mostly for STM32

All that changes is where you used to go:

> #include <SFE_BMP180.h>
> #include <Wire.h>
>
> SFE_BMP180 pressure;


You now go 
> &#35;include &lt;SFE_BMP180_hw.h&gt;
> 
> HardWire HWire(1, I2C_FAST_MODE);
> SFE_BMP180_hw pressure(&HWire);

If you want to use bus 2, you just go:

> #include <SFE_BMP180_hw.h>
> 
> HardWire HWire(2, I2C_FAST_MODE);
> SFE_BMP180_hw pressure(&HWire);

Simples! Thanks Sparkfun for the excelent library

Love, Takigama

Playbulb Bluetooth Codes
====================

0x0003: get name
---------------------
0x001c: Get / Set Name
---------------------
Value: Name of device in Hex


0x0016: Effects
---------------------
Value: [white][color][mode][00][speed]

Parameter  | Value
------------- | -------------
white | 00 => off, ff => white, 01-> ff => saturation of white
color | color as RGB hex
mode  | 00 = Flash, 01 = Pulse, 02 = Rainbow Jump, 03 = Rainbow Fade
speed | 46 46-> 01 01 => Slow to Fast (Flash, Rainbow), 1e 1e-> 01 01 => Slow to Fast (Pulse)

#####Red pulse effect
00ff000001000f0f


0x0018: Get / Set Color
---------------------
Value: [white][color]

Parameter  | Value
------------- | -------------
white | 00 => off, ff => white, 01-> ff => saturation of white
color | color as RGB hex

#####Example
00ff0000 => full red
ff000000 => white


0x0023: Candle Type
---------------------
Return Value  | Interpretation
------------- | -------------
BTL300  | Playbulb Candle


0x0025: Microprocessor Family
---------------------
#####Example Response
`CSR101x A05`

http://www.csr.com/products/csr101x-product-family


0x0027: Get Firmware Version
---------------------
#####Example Response
`BTL300_v5`


0x0029: Application Version
---------------------
#####Example Response
`Application version 2.3.0.31`


0x002b: ??
---------------------
#####Example Response
`Mipow Limited`


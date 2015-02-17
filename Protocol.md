Playbulb Bluetooth Codes
====================
0x0003: get name
---------------------
0x001c: Get / Set Name
---------------------
Value: Name of device in Hex


0x0014: Effects
---------------------
Value: [saturation][color][mode][00][speed][00]

Parameter  | Value
------------- | -------------
saturation | ff=low, 00= high
color | color as rgb hex
mode  | 01 = Fade, 02 = Jump rbg, 03 = Fade RGB, 04 = Candle Effekt
speed | 00-> ff, 00 => really slow, 01 => really fast, 02 => slower

#####Candle effekt
`saturation + color = ff000000`


0x0016: Get / Set Color
---------------------
Value  | Result
------------- | -------------
00000000 | led off
ff000000 | candle color
00+hex  | hex color

#####Example
00ff0000 => full red


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


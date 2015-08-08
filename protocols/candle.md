Playbulb Bluetooth Codes
====================

0x0003: get name
---------------------
0x001c: Get / Set Name
---------------------
Value: Name of device in Hex

0x0014: Effects
---------------------
Long: 0000fffc-0000-1000-8000-00805f9b34fb

Short: fffc

Value: [white][red][green][blue][mode][00][speed][00]

Parameter  | Value
------------- | -------------
white (seems like saturation) | 0x00 (off) .. 0xff (full)
red | 0x00 (off) .. 0xff (full)
green | 0x00 (off) .. 0xff (full)
blue | 0x00 (off) .. 0xff (full)
mode  | 01 = Fade, 02 = Jump RBG (rainbow), 03 = Fade RGB (rainbow), 04 = Candle Effect
speed | 00-> ff, 00 => really slow, 01 => really fast, 02 => slower

#####Example
Value  | Result
------------- | -------------
ff00000004000000 | candle effect


0x0016: Get / Set Color
---------------------
Long:

Short:

Value: [white][red][green][blue]

Parameter  | Value
------------- | -------------
white (seems like saturation) | 0x00 (off) .. 0xff (full)
red | 0x00 (off) .. 0xff (full)
green | 0x00 (off) .. 0xff (full)
blue | 0x00 (off) .. 0xff (full)

#####Example
Value  | Result
------------- | -------------
00000000 | led off
ff000000 | full white
00ff0000 | full red
0000ff00 | full green
000000ff | full blue
ffffffff | max brightness white + mixed white

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


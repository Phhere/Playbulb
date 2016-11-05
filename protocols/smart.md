Playbulb Colour LED Bluetooth Codes
===================================

http://www.mipow.de/smart-home/46/mipow-playbulb-smart

0x0003: Get name
----------------
#####Example response
4d 49 50 4f 57 20 53 4d 41 52 54 20 42 55 4c 42 -> MIPOW SMART BULB

0x001F: Get / Set Name
----------------------
#####Example response
04 ff ff 04 ff ff 04 ff ff 04 ff ff 00 00


0x0019: Effects
---------------
Value: [white][color][mode][00][speed]

Parameter | Value
--------- | -------------
white     | 00 => off, ff => white, 01 -> ff => saturation of white
color     | color as RGB hex
mode      | 00 = Flash, 01 = Pulse, 02 = Rainbow Jump, 03 = Rainbow Fade
not used  | 00
speed     | 46 46 -> 01 01 => Slow to Fast (Flash, Rainbow), 1e 1e -> 01 01 => Slow to Fast (Pulse)

#####Example response
00 ff 00 00 01 00 0f 0f

**Examples** to use with `gatttool -I`
- Off: `char-write-cmd 0x0019 0000000000000000`
- Red pulse effect: `char-write-cmd 0x0019 00ff000001000f0f`
- Green flash effect: `char-write-cmd 0x0019 0000ff0000000f0f`
- White pulse effect: `char-write-cmd 0x0019 ff00000001000f0f`
- Rainbow jump effect: `char-write-cmd 0x0019 00ff000002000f0f`

0x001b: Get / Set Color (updated)
-----------------------
Value: [white][color]

Parameter | Value
--------- | -------------
white     | 00 => off, ff => white, 01 -> ff => saturation of white
color     | color as RGB hex

#####Example response
00 ff 00 ff

**Examples** to use with `gatttool -I`
- Off: `char-write-cmd 0x001b 00000000`
- Full white: `char-write-cmd 0x001b ff000000`
- Full red: `char-write-cmd 0x001b 00ff0000`
- Full green: `char-write-cmd 0x001b 0000ff00`
- Full blue: `char-write-cmd 0x001b 000000ff`

0x0021: Get Name
----------------------
##### Example response
4d 49 50 4f 57 20 53 4d 41 52 54 20 42 55 4c 42 --> 'MIPOW SMART BULB'

0x0028: Microprocessor Family
-----------------------------
#####Example response
42 54 4c 32 30 31 -> `BTL201`


0x0030: Vendor
-----------------------------
4d 69 70 6f 77 20 4c 69 6d 69 74 65 64 -> `Mipow Limited`

0x002a: Get Firmware Version
----------------------------
#####Example response
43 53 52 31 30 31 78 20 41 30 35 -> `CSR101x A05`


0x002c: Microprocessor Version
------------------------------
#####Example response
42 54 4c 32 30 31 5f 76 32 -> `BTL201_v2`


0x002e: Application Version
---------------------------
#####Example response
41 70 70 6c 69 63 61 74 69 6f 6e 20 76 65 72 73 69 6f 6e 20 32 2e 34 2e 33 2e 32 36 -> `Application version 2.3.3.26`


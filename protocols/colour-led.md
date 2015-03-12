Playbulb Colour LED Bluetooth Codes
===================================

http://www.playbulb.com/en/playbulb-color.html#meet-playbulb-color

0x0003: Get name
----------------
**Example response**
50 4c 41 59 42 55 4c 42 20 43 4f 4c 4f 55 52 20 4c 45 44 -> PLAYBULB COLOUR LED

0x001c: Get / Set Name
----------------------
**Example response**
04 ff ff 04 ff ff 04 ff ff 04 ff ff 00 00


0x0010: ?
---------
**Example response**
00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00


0x0011: ?
---------
**Example response**
0a 12 00 f9 ff


0x0012: ?
---------
**Example response**
00 00 00 ff ff ff ff 00 00 00 00 00 00


0x0013: ?
---------
**Example response**
06 14 00 fa ff


0x0015: ?
---------
**Example response**
06 16 00 fb ff


0x0016: Effects
---------------
Value: [white][color][mode][00][speed]

Parameter | Value
--------- | -------------
white     | 00 => off, ff => white, 01 -> ff => saturation of white
color     | color as RGB hex
mode      | 00 = Flash, 01 = Pulse, 02 = Rainbow Jump, 03 = Rainbow Fade
not used  | 00
speed     | 46 46 -> 01 01 => Slow to Fast (Flash, Rainbow), 1e 1e -> 01 01 => Slow to Fast (Pulse)

**Example response**
00 ff 00 00 01 00 0f 0f

**Example** to use with `gatttool -I`
- Off: `char-write-cmd 0x0016 0000000000000000`
- Red pulse effect: `char-write-cmd 0x0016 00ff000001000f0f`
- Green flash effect: `char-write-cmd 0x0016 0000ff0000000f0f`
- White pulse effect: `char-write-cmd 0x0016 ff00000001000f0f`
- Rainbow jump effect: `char-write-cmd 0x0016 00ff000002000f0f`

0x0017: ?
---------
**Example response**
06 18 00 fc ff

0x0018: Get / Set Color
-----------------------
Value: [white][color]

Parameter | Value
--------- | -------------
white     | 00 => off, ff => white, 01 -> ff => saturation of white
color     | color as RGB hex

**Example response**
00 ff 00 ff

**Examples** to use with `gatttool -I`
- Off: `char-write-cmd 0x0018 00000000`
- Full white: `char-write-cmd 0x0018 ff000000`
- Full red: `char-write-cmd 0x0018 00ff0000`
- Full green: `char-write-cmd 0x0018 0000ff00`
- Full blue: `char-write-cmd 0x0018 000000ff`


0x0025: Microprocessor Family
-----------------------------
**Example Response**
42 54 4c 31 30 30 43 -> `BTL100C`


0x0027: Get Firmware Version
----------------------------
**Example Response**
43 53 52 31 30 31 78 20 41 30 35 -> `CSR101x A05`


0x0029: Microprocessor Version
------------------------------
**Example Response**
42 54 4c 31 30 30 43 5f 76 36 -> `BTL100C_v6`


0x002b: Application Version
---------------------------
**Example Response**
41 70 70 6c 69 63 61 74 69 6f 6e 20 76 65 72 73 69 6f 6e 20 32 2e 33 2e 30 2e 33 31 -> `Application version 2.3.0.31`


Playbulb Bluetooth Codes
====================

0x0003: Get name
----------------
#####Example response
50 4c 41 59 42 55 4c 42 -> `PLAYBULB`

0x0010: set brightness
---------------------

Value: [level]

Parameter  | Value
------------- | -------------
brightness | 0100-> 0114, 0100 => low, 0114 => high


**Examples** to use with `gatttool -I`
- Off: `char-write-cmd 0x0010 0100`
- On (full brightness): `char-write-cmd 0x0010 0114`


0x0016: Get name (same than 0x0003)
---------
#####Example response
50 4c 41 59 42 55 4c 42 -> `PLAYBULB`

0x0021: Microprocessor Version
-----------------------------
#####Example response
42 54 4c 31 30 30 41 5f 76 31 32 -> `BTL100A_v12`

0x0023: Application Version
---------
#####Example response
41 70 70 6c 69 63 61 74 69 6f 6e 20 76 65 72 73 69 6f 6e 20 32 2e 33 2e 30 2e 33 31 -> `Application version 2.3.0.31`

0x0025: Manufacturer
---------
#####Example response
4d 69 70 6f 77 20 4c 69 6d 69 74 65 64 -> `Mipow Limited`

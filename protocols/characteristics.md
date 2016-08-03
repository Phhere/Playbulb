###Playbulb characteristics uuid (XXXX-0000-1000-8000-00805f9b34fb)

UUID     | Description                                                   | Example                          | URL | 
---------| ------------------------------------------------------------- | -------------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
00002a00 | Name of device                                                | My candle                        | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.gap.device_name.xml) |
00002a01 | Appearance                                                    | 40 03                            | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.gap.appearance.xml) |
00002a04 | Peripheral Preferred Connection Parameters                    | 10 00 20 00 00 00 58 02          | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.gap.peripheral_preferred_connection_parameters.xml) |
00002a05 | Service Changed                                               | 05 00 ff ff                      | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.gatt.service_changed.xml) |
00002a19 | Battery Level                                                 | 64                               | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.battery_level.xml) | 
00002a25 | Playbulb model                                                | BTL300                           | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.serial_number_string.xml) |
00002a26 | Firmware version                                              | BTL300_v6                        | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.firmware_revision_string.xml) |
00002a27 | Microprocessor                                                | CSR101x A05                      | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.hardware_revision_string.xml) |
00002a28 | Application version                                           | Application version 2.4.3.26     | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.software_revision_string.xml) |
00002a29 | Manufacturer                                                  | Mipow Limited                    | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.manufacturer_name_string.xml) |
00002a50 | PnP ID                                                        | 0a 33 00 a5 a5 00 5b 02 00 23 9b e1 11 02 d1 13 10 00 00 | [doc](https://www.bluetooth.com/specifications/gatt/viewer?attributeXmlFile=org.bluetooth.characteristic.pnp_id.xml) |
0000fff8 | ???                                                           | 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 | | 
0000fff9 | ???                                                           | 00 00 00 ff ff ff ff 00 00 00 00 00 00 | | 
0000fffa | ???                                                           | 00 | | 
0000fffb | Get / Set Color with effects [WRGBE-S-]                       | FF 00 00 00 04 00 01 00 | | 
0000fffc | Get / Set Color [WRGB]                                        | FF 00 00 00 | |
0000fffd | ???                                                           | b7 22 b2 e0 | | 
0000fffe | ???                                                           | 04 ff ff 04 ff ff 04 ff ff 04 ff ff 00 00 | | 
0000ffff | Device name (same as 2a00)                                    | His candle | | 

### Get / Set Color (0000fffc-0000-1000-8000-00805f9b34fb)

Value: [white][red][green][blue]

Parameter  | Value
------------- | -------------
white | 0x00 (off) .. 0xff (full)
red   | 0x00 (off) .. 0xff (full)
green | 0x00 (off) .. 0xff (full)
blue  | 0x00 (off) .. 0xff (full)

#####Example
Value  | Result
------------- | -------------
00000000 | led off
ff000000 | full white
00ff0000 | full red
0000ff00 | full green
000000ff | full blue
ffffffff | max brightness white + mixed white

###Set colors with effects

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
ff00000004000000 | white candle effect

###Microprocessor

http://www.csr.com/products/csr101x-product-family

###Bluetooth characteristics table

https://www.bluetooth.com/specifications/gatt/characteristics

###Playbulb Sphere (BTL301W):

```
[LE]> characteristics
handle: 0x0002, char properties: 0x0a, char value handle: 0x0003, uuid: 00002a00-0000-1000-8000-00805f9b34fb
handle: 0x0004, char properties: 0x02, char value handle: 0x0005, uuid: 00002a01-0000-1000-8000-00805f9b34fb
handle: 0x0006, char properties: 0x02, char value handle: 0x0007, uuid: 00002a04-0000-1000-8000-00805f9b34fb
handle: 0x0009, char properties: 0x22, char value handle: 0x000a, uuid: 00002a05-0000-1000-8000-00805f9b34fb
handle: 0x000d, char properties: 0x10, char value handle: 0x000e, uuid: 00002a37-0000-1000-8000-00805f9b34fb
handle: 0x0010, char properties: 0x0e, char value handle: 0x0011, uuid: 00002a39-0000-1000-8000-00805f9b34fb
handle: 0x0012, char properties: 0x02, char value handle: 0x0013, uuid: 0000fff8-0000-1000-8000-00805f9b34fb
handle: 0x0014, char properties: 0x0a, char value handle: 0x0015, uuid: 0000fff9-0000-1000-8000-00805f9b34fb
handle: 0x0016, char properties: 0x06, char value handle: 0x0017, uuid: 0000fffa-0000-1000-8000-00805f9b34fb
handle: 0x0018, char properties: 0x06, char value handle: 0x0019, uuid: 0000fffb-0000-1000-8000-00805f9b34fb
handle: 0x001a, char properties: 0x06, char value handle: 0x001b, uuid: 0000fffc-0000-1000-8000-00805f9b34fb
handle: 0x001c, char properties: 0x0a, char value handle: 0x001d, uuid: 0000fffd-0000-1000-8000-00805f9b34fb
handle: 0x001e, char properties: 0x0a, char value handle: 0x001f, uuid: 0000fffe-0000-1000-8000-00805f9b34fb
handle: 0x0020, char properties: 0x0a, char value handle: 0x0021, uuid: 0000ffff-0000-1000-8000-00805f9b34fb
handle: 0x0023, char properties: 0x12, char value handle: 0x0024, uuid: 00002a19-0000-1000-8000-00805f9b34fb
handle: 0x0027, char properties: 0x02, char value handle: 0x0028, uuid: 00002a25-0000-1000-8000-00805f9b34fb
handle: 0x0029, char properties: 0x02, char value handle: 0x002a, uuid: 00002a27-0000-1000-8000-00805f9b34fb
handle: 0x002b, char properties: 0x02, char value handle: 0x002c, uuid: 00002a26-0000-1000-8000-00805f9b34fb
handle: 0x002d, char properties: 0x02, char value handle: 0x002e, uuid: 00002a28-0000-1000-8000-00805f9b34fb
handle: 0x002f, char properties: 0x02, char value handle: 0x0030, uuid: 00002a29-0000-1000-8000-00805f9b34fb
handle: 0x0031, char properties: 0x02, char value handle: 0x0032, uuid: 00002a50-0000-1000-8000-00805f9b34fb
handle: 0x0034, char properties: 0x0a, char value handle: 0x0035, uuid: 00001013-d102-11e1-9b23-00025b00a5a5
handle: 0x0036, char properties: 0x08, char value handle: 0x0037, uuid: 00001018-d102-11e1-9b23-00025b00a5a5
handle: 0x0038, char properties: 0x12, char value handle: 0x0039, uuid: 00001014-d102-11e1-9b23-00025b00a5a5
handle: 0x003b, char properties: 0x02, char value handle: 0x003c, uuid: 00001011-d102-11e1-9b23-00025b00a5a5
```

###Playbulb Candle (BLT300)

```
handle: 0x0002, char properties: 0x0a, char value handle: 0x0003, uuid: 00002a00-0000-1000-8000-00805f9b34fb
handle: 0x0004, char properties: 0x02, char value handle: 0x0005, uuid: 00002a01-0000-1000-8000-00805f9b34fb
handle: 0x0006, char properties: 0x02, char value handle: 0x0007, uuid: 00002a04-0000-1000-8000-00805f9b34fb
handle: 0x0009, char properties: 0x22, char value handle: 0x000a, uuid: 00002a05-0000-1000-8000-00805f9b34fb
handle: 0x000d, char properties: 0x10, char value handle: 0x000e, uuid: 00002a37-0000-1000-8000-00805f9b34fb
handle: 0x0010, char properties: 0x02, char value handle: 0x0011, uuid: 0000fff8-0000-1000-8000-00805f9b34fb
handle: 0x0012, char properties: 0x0a, char value handle: 0x0013, uuid: 0000fff9-0000-1000-8000-00805f9b34fb
handle: 0x0014, char properties: 0x06, char value handle: 0x0015, uuid: 0000fffa-0000-1000-8000-00805f9b34fb
handle: 0x0016, char properties: 0x06, char value handle: 0x0017, uuid: 0000fffb-0000-1000-8000-00805f9b34fb
handle: 0x0018, char properties: 0x06, char value handle: 0x0019, uuid: 0000fffc-0000-1000-8000-00805f9b34fb
handle: 0x001a, char properties: 0x0a, char value handle: 0x001b, uuid: 0000fffd-0000-1000-8000-00805f9b34fb
handle: 0x001c, char properties: 0x0a, char value handle: 0x001d, uuid: 0000fffe-0000-1000-8000-00805f9b34fb
handle: 0x001e, char properties: 0x0a, char value handle: 0x001f, uuid: 0000ffff-0000-1000-8000-00805f9b34fb
handle: 0x0021, char properties: 0x12, char value handle: 0x0022, uuid: 00002a19-0000-1000-8000-00805f9b34fb
handle: 0x0025, char properties: 0x02, char value handle: 0x0026, uuid: 00002a25-0000-1000-8000-00805f9b34fb
handle: 0x0027, char properties: 0x02, char value handle: 0x0028, uuid: 00002a27-0000-1000-8000-00805f9b34fb
handle: 0x0029, char properties: 0x02, char value handle: 0x002a, uuid: 00002a26-0000-1000-8000-00805f9b34fb
handle: 0x002b, char properties: 0x02, char value handle: 0x002c, uuid: 00002a28-0000-1000-8000-00805f9b34fb
handle: 0x002d, char properties: 0x02, char value handle: 0x002e, uuid: 00002a29-0000-1000-8000-00805f9b34fb
handle: 0x002f, char properties: 0x02, char value handle: 0x0030, uuid: 00002a50-0000-1000-8000-00805f9b34fb
handle: 0x0032, char properties: 0x0a, char value handle: 0x0033, uuid: 00001013-d102-11e1-9b23-00025b00a5a5
handle: 0x0034, char properties: 0x08, char value handle: 0x0035, uuid: 00001018-d102-11e1-9b23-00025b00a5a5
handle: 0x0036, char properties: 0x12, char value handle: 0x0037, uuid: 00001014-d102-11e1-9b23-00025b00a5a5
handle: 0x0039, char properties: 0x02, char value handle: 0x003a, uuid: 00001011-d102-11e1-9b23-00025b00a5a5
```

Examples
========

Linux
-----

First check the HCI device is up and running

```shell
sudo hciconfig
```

`hci0:	Type: BR/EDR  Bus: USB
 	BD Address: 00:1A:7D:DA:71:08  ACL MTU: 310:10  SCO MTU: 64:8
 	UP RUNNING PSCAN
 	RX bytes:80815 acl:0 sco:0 events:2559 errors:0
 	TX bytes:1372 acl:5 sco:0 commands:83 errors:0
`

If the device is showing like this you are good to go.
When it is showing as DOWN, you can bring it up with

```shell
sudo hciconfig hci0 up
```

Let's start a scan for LE devices

```shell
sudo hcitool lescan
```

`
AC:E6:4B:06:2C:55 PLAYBULB CANDLE
AC:E6:4B:06:66:9A (unknown)
AC:E6:4B:06:66:9A PLAYBULB CANDLE
`

You have to kill it with CTRL+C

Now you can use the Device MAC and set a new color or effect
The following command will set the color to green

`gatttool -b AC:E6:4B:06:2C:55 --char-write -a 0x0016 -n 0000ff00`

The next command will set the the effect to flash, and color to red

`gatttool -b AC:E6:4B:06:2C:55 --char-write -a 0x0014 -n 00ff000000001f00`


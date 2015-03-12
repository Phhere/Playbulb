General
=======

While trying to decode the BT protocol used, we came across some weird behaviours.
It looks like the group feature is an App only feature.
There was no information we could find so far in the BT traffic which would point to a group handle.
What we believe is happening, and could also see in the BT traffic, is that once you group a few Candles together,
and you change something in that group, like color or effect, we see the same command being send to all devices in
that group.

Another thing we discovered is that if you have a group setup, and are actively using the App to do changes on the
group, you are not able to connect to any of the group members from a Linux system while the App is still open.
There will be error messages visible like this:

`Transport endpoint is not connected (107`

So you have to close the group setting page within the App first.
This might also happen for a single device if you have the device setting page open.

At the moment this is all Linux only.
To use the examples provided, you need BlueZ installed on your system, and have a BT4.0 USB Dongle or builtin BT.

Here is a list of Device IDs which we know are working:

- ID 0a12:0001 Cambridge Silicon Radio, Ltd Bluetooth Dongle (HCI mode)
- Builtin BT of ThinkPad T440s
- Builtin BT of Lenovo Yoga 2 Pro

When it comes to the BlueZ version, we could see some issue with the latest BlueZ 5.x
We were not able to directly write to the device using `gatttool`

On Ubuntu 14.10.1, which I use for testing, I had to stick to the distro default version, which as of writting this, is
`4.101-0ubuntu20`.
To get the `gatttool` on a Fedora system, you need at least 5.28 of the BlueZ package which is only available for Fedora 22+.

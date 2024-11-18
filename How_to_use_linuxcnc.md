# MPG_Joypad
MPG_Joypad is a handheld device used in LINUXCNC systems to control axis movement manually.



7
hal_input - control HAL pins with any Linux input device, including USB HID devices








# Debian Linuxcnc Test Lab


1st # find the ID

Bus 001 Device 013: ID 0079:0006 DragonRise Inc. PC TWIN SHOCK Gamepad



Find out more details

```
less /proc/bus/input/devices
```



I: Bus=0003 Vendor=0079 Product=0006 Version=0110
N: Name="Microntek              USB Joystick          "
P: Phys=usb-0000:00:14.0-8/input0
S: Sysfs=/devices/pci0000:00/0000:00:14.0/usb1/1-8/1-8:1.0/0003:0079:0006.000F/input/input30
U: Uniq=
H: Handlers=event16 js0 
B: PROP=0
B: EV=20001b
B: KEY=fff00000000 0 0 0 0
B: ABS=30027
B: MSC=10
B: FF=107030000 0


# perfect

halcmd loadusr -W hal_input -KRAL "Microntek              USB Joystick          "
note: name is 'Microntek              USB Joystick          '




# perfect

halcmd loadusr -W hal_input -KRAL "Vendor=0079 Product=0006"
halcmd loadusr -W hal_input -KRAL "14.0-8/input0"




# try not work


halcmd loadusr -W hal_input -KRAL "usb-0000:00:14.0-8/input0"
halcmd loadusr -W hal_input -KRAL "0079:0006.000F/input/input30"





halmeter

setp input.0.abs-hat0y_scale -1




IF two joystck same brand how to fix that errors???




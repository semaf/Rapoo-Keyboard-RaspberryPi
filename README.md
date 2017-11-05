# Rapoo Bluetooth Keyboard setup on Raspberry Pi
## Setup the Keyboard
```terminal
pi@raspberrypi:~ $ sudo bluetoothctl 
[NEW] Controller B8:2A:7D:DA:11:13 raspberrypi [default]

[bluetooth]# agent on
Agent registered

[bluetooth]# pairable on
Changing pairable on succeeded

[bluetooth]# scan on
Discovery started
[NEW] Device 6C:5C:63:21:60:76 6C-5C-63-21-60-76
[CHG] Device 6C:5C:63:21:60:76 LegacyPairing: no
[CHG] Device 6C:5C:63:21:60:76 Name: E6350
[CHG] Device 6C:5C:63:21:60:76 Alias: E6350
[CHG] Device 6C:5C:63:21:60:76 LegacyPairing: yes
...

[bluetooth]# scan off
Discovery stopped

[bluetooth]# pair 6C:5C:63:21:60:76
Attempting to pair with 6C:5C:63:21:60:76
[CHG] Device 6C:5C:63:21:60:76 Connected: yes
[agent] PIN code: 963064

  --> Entern Pin + Return on Keyboard <--

[CHG] Device 6C:5C:63:21:60:76 Paired: yes
Pairing successful

[bluetooth]# trust 6C:5C:63:21:60:76
Changing 6C:5C:63:21:60:76 trust succeeded

[bluetooth]# connect 6C:5C:63:21:60:76
Attempting to connect to 6C:5C:63:21:60:76
Connection successful

[bluetooth]# info 6C:5C:63:21:60:76
Device 6C:5C:63:21:60:76
	Name: E6350
	Alias: E6350
	Class: 0x002540
	Icon: input-keyboard
	Paired: yes
	Trusted: yes
	Blocked: no
	Connected: no
	LegacyPairing: yes
	UUID: Service Discovery Serve.. (00001000-0000-1000-8000-00805f9b34fb)
	UUID: Human Interface Device... (00001124-0000-1000-8000-00805f9b34fb)
	UUID: PnP Information           (00001200-0000-1000-8000-00805f9b34fb)
	Modalias: usb:v0A5Cp8502d011B

[bluetooth]# exit
```


## Change Keyboard Language

```terminal
pi@raspberrypi:~ $ sudo nano /etc/default/keyboard
````

Change the line:
```terminal
XKBLAYOUT=”gb”
````
to 
```terminal
XKBLAYOUT=”de”
````
and save
```terminal
pi@raspberrypi:~ $ sudo reboot
````

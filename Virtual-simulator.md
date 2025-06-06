# gerEFI Virtual simulator

    **You'll be able to test out the gerEFI controller on your computer**

gerEFI virtual firmware simulator is a way to play with the gerEFI without any hardware!
This simulator allows you to see how the firmware reacts to different commands and configuration adjustments via Tuner Studio. The main thing one would be looking at would be the 'Engine Sniffer'.

All you need is a Windows computer. This virtual simulator is built from the same source code as gerEFI controllers firmware.

The gerEFI console runs on Java, so if you don't have that installed on your PC you'll need to download it.
If you don't have the gerEFI console you can download it [here](https://gerefi.com/build_server/gerefi_bundle_f407-discovery.zip).  
You'll have to unzip the file and go into the console folder.

 ![Directory](FAQ/images/simulator/gerEFI_console_directory.png)

 And then open the gerefi_console.jar file.

 ![Contents](FAQ/images/simulator/gerEFI_console_directionary_files.png)

After this, you'll start the virtual simulator.

![gerEFI_start](FAQ/images/simulator/gerEFI_start.png)

## Connecting the simulator to Tunerstudio

There are two ways to connect gerEFI virtual simulator to Tunerstudio, it all depends on whether you have the lite or commercial version.

To start off you'll need to open one of your existing projects or just create a new one.

If you don't know how to create a Tunerstudio project go [here](HOWTO-create-tunerstudio-project)

With the paid version all you need to do is to go into the communication settings inside a created project

 ![Communication_settings](FAQ/images/simulator/Tunerstudio_comm._settings.png)

choose the driver "Standard Protocols Driver" and connection type "TCP/IP - WiFi driver", enter the Port as "29002" and the IP address as "localhost" (aka 127.0.0.1)

 ![Communication_settings](FAQ/images/simulator/Communication_settings_direct.png)

**However, if you only have the lite version of Tunerstudio the process will be different.**

## Emulating a serial port to connect to Tunerstudio lite

If you prefer using the free version of Tunerstudio - Tunerstudio lite -  you'll need to install a serial port emulator
from [here](https://www.hw-group.com/software/hw-vsp3-virtual-serial-port#download).
After download, install it, then run the configuration application "HW Virtual Serial Port".

- switch from "read only access" to "admin access" by clicking "Login" button
- choose a port name, COM100 for example, and change the port address to 29002.

![Virtual serial port](FAQ/images/simulator/Emulator_settings.png)

Now you can create your virtual port.

![Virtual_port_start](FAQ/images/simulator/Virtual_port_start.png)

So now if you open the communication settings in Tunerstudio,

![Communication_settings](FAQ/images/simulator/Tunerstudio_comm._settings.png)

you'll be able to connect to your emulator.

![Emulated Communication settings](FAQ/images/simulator/Communication_settings_tutorial.png)

Now if your virtual simulator is connected to Tunerstudio you'll see a green zero in your gerEFI virtual simulator.

![Connected virtual simulator](FAQ/images/simulator/gerEFI_virtual_simulator_connected.png)

## Troubleshooting

In case something does not work with the TCP<>Serial driver, first thing is to make sure that gerefi_simulator.exe is in the list of Processes in Task Manager

Next step is executing

`telnet localhost 29001`

to make sure that dev console protocol is alive

and

`telnet localhost 29002`

to make sure that Tunerstudio protocol is alive.

Expected behavior is that connection would be established. If it does not, you might need to look in firewall settings.

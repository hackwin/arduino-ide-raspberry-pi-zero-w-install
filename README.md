# arduino-ide-raspberry-pi-zero-w-install
How to get Arduino IDE working on a Raspberry Pi Zero W

The following error message can appear when trying to install Arduino IDE on Raspberry Pi Zero W.

`Error occurred during initialization of VM`<br>
`Server VM is only supported on ARMv7+ VFP`

Java 11 does not support the ARM processor in the Pi Zero.

# Steps to Fix Problem
1. Install Raspbian Linux OS to SD Card
1. Open the command terminal
1. Run `sudo apt-get install openjdk-8-jre-zero -y`

1. Comment out line "assistive_technologies=..." in "/etc/java-8-openjdk/accessibility.properties"
	1. using `vi`, press Insert key, add "#" to the line, Esc key, Press "wq" and press Enter key

1. Run `sudo apt-get install arduino -y`
1. Run `sudo update-alternatives --all`
	1. Keep pressing Enter key until you see lines about java
	1. Press the corresponding number for "java-8-openjdk...".  This occurs about 8 times out of 20.
	
1. Run `arduino` at the command terminal

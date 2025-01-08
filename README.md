10 Tips for Building a DUCO (Duino-Coin) Mining Rig
Understand Duino-Coin Basics
Duino-Coin is a cryptocurrency designed for low-power devices like Arduino boards, Raspberry Pis, and ESP microcontrollers. It prioritizes energy-efficient mining.

Choose the Right Hardware
Start with devices like Arduino Nano, UNO, ESP8266/ESP32, or Raspberry Pi. These are compatible and ideal for low-energy mining.

Use I2C for Device Connectivity
Use the I2C (Inter-Integrated Circuit) protocol to connect multiple microcontrollers (e.g., Arduino boards) in a master-slave configuration. This reduces the number of GPIO pins used and simplifies wiring.

The master device (e.g., Raspberry Pi or main Arduino) controls communication.
Assign unique addresses to each slave device to avoid conflicts.
Scale with Multiple Devices
Add more devices (connected via USB, WiFi, or I2C) to scale up your mining rig. Each device contributes additional hash power.

Optimize Software for I2C Communication
Modify the Duino-Coin miner script to enable I2C communication if connecting devices via this protocol. Ensure the miner recognizes each device as an individual worker.

Power Efficiency
Use a stable power source to run multiple devices. A powered USB hub or a 5V DC adapter is recommended for setups with many connected devices.

Use Low-Power Hosts
Run the mining controller software on a Raspberry Pi, which consumes significantly less power than a standard PC.

Monitor and Troubleshoot
Set up the Duino-Coin wallet or web dashboard to monitor your mining devices. Track hash rates and uptime to ensure everything runs smoothly.

Ensure Proper Cooling
Position your mining rig in a well-ventilated area, as devices running 24/7 may overheat. Use small cooling fans if necessary.

Community Support
Join the active Duino-Coin community via Discord or forums for help, troubleshooting, and updates.

Using I2C for Connecting Devices
Benefits of I2C in Mining Rigs
Reduced Wiring: I2C only requires two communication lines (SCL for clock and SDA for data) alongside power (VCC/GND).
Scalability: Up to 127 devices can be connected to a single master.
Ease of Expansion: Adding new devices is straightforward with minimal changes to wiring or code.
Version 4.0 reward goals
Captured at normal multiplier (no weekend boost)

Device	Hashrate	Threads	DUCO/day	Power usage
Arduino	343 H/s	1	12	<0.5 W
ESP32	170-180 kH/s	2	10	1.5-2 W
ESP32-S2/C3	85-96 kH/s	1	8	1-1.5 W
ESP8266	66 kH/s	1	6	1-1.5 W
Raspberry Pi 4 (LOW)	1 MH/s (no fasthash)	4	6-7	6.5 W
Raspberry Pi 4 (MED)	5.4 MH/s (fasthash)	4	7-8	6.5 W
Low power PCs		4	4-6	-
Medium		4-8	6-10	-
High end		8+	10-12	-

How to Connect Multiple Devices
Using USB Hubs
For Arduino devices, connect via a powered USB hub to ensure stable power and communication with the host computer.
Using WiFi-Enabled Devices
ESP8266/ESP32 devices connect directly to the Duino-Coin network via WiFi, bypassing physical connections.
Using I2C
Wire all devices as described above.
Use the master to collect hash data from slaves and relay it to the Duino-Coin network.
This approach is especially useful for large rigs with multiple low-power microcontrollers.

<!--
*** Official Duino Coin README
*** by revoxhere, 2019-present
-->

<a href="https://duinocoin.com">
  <img src="https://github.com/revoxhere/duino-coin/blob/master/Resources/duco.png?raw=true" width="215px" align="right" />
</a>

<h3>
  <a href="https://duinocoin.com">
    <img src="https://github.com/revoxhere/duino-coin/blob/master/Resources/ducobanner.png?raw=true" width="430px" />
  </a>
  <h3>
   Simple, eco-friendly, centralized coin that can be mined with Arduinos, ESP boards, Raspberry Pis, computers, and many more 
  (including Wi-Fi routers, smart TVs, smartphones, smartwatches, SBCs and other MCUs).
  

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

How to Connect Multiple Devices
Using USB Hubs
For Arduino devices, connect via a powered USB hub to ensure stable power and communication with the host computer.
Using WiFi-Enabled Devices
ESP8266/ESP32 devices connect directly to the Duino-Coin network via WiFi, bypassing physical connections.
Using I2C
Wire all devices as described above.
Use the master to collect hash data from slaves and relay it to the Duino-Coin network.
This approach is especially useful for large rigs with multiple low-power microcontrollers.

## Version 4.0 reward goals

Captured at normal multiplier (no weekend boost)
| Device                | Hashrate            | Threads | DUCO/day | Power usage |
|-----------------------|---------------------|---------|----------|-------------|
| Arduino               | 343 H/s             | 1       | 12       | <0.5 W
| ESP32                 | 170-180 kH/s        | 2       | 10       | 1.5-2 W
| ESP32-S2/C3           | 85-96 kH/s          | 1       | 8        | 1-1.5 W
| ESP8266               | 66 kH/s             | 1       | 6        | 1-1.5 W
| Raspberry Pi 4 (LOW)  | 1 MH/s (no fasthash)| 4       | 6-7      | 6.5 W
| Raspberry Pi 4 (MED)  | 5.4 MH/s (fasthash) | 4       | 7-8      | 6.5 W
| Low power PCs         |                     | 4       | 4-6      | -
| Medium                |                     | 4-8     | 6-10     | -
| High end              |                     | 8+      | 10-12    | -

<details>
  <summary><b>Other tested devices and their benchmarks</b></summary>
  
Please note the DUCO/day column has been removed since version 4.0 changed the reward system.
| Device/CPU/SBC/MCU/chip                                   | Average hashrate<br>(all threads) | Mining<br>threads | Power<br>usage |
|-----------------------------------------------------------|-----------------------------------|-------------------|----------------|
| Raspberry Pi Pico                                         | 5 kH/s                            | 1                 | 0.3 W          |
| Raspberry Pi Zero                                         | 18 kH/s                           | 1                 | 1.1 W          |
| Raspberry Pi 3 **(32bit)**                                | 440 kH/s                          | 4                 | 5.1 W          |
| Raspberry Pi 4 **(32bit)**                                | 740 kH/s                          | 4                 | 6.4 W          |
| Raspberry Pi 4 **(64bit, fasthash)**                      | 6.8 MH/s                          | 4                 | 6.4 W          |
| ODROID XU4                                                | 1.0 MH/s                          | 8                 | 5 W            |
| Atomic Pi                                                 | 690 kH/s                          | 4                 | 6 W            |
| Orange Pi Zero 2                                          | 740 kH/s                          | 4                 | 2.55 W         |
| Khadas Vim 2 Pro                                          | 1.12 MH/s                         | 8                 | 6.2 W          |
| Libre Computers Tritium H5CC                              | 480 kH/s                          | 4                 | 5 W            |
| Libre Computers Le Potato                                 | 410 kH/s                          | 4                 | 5 W            |
| Pine64 ROCK64                                             | 640 kH/s                          | 4                 | 5 W            |
| Intel Celeron G1840                                       | 1.25 MH/s                         | 2                 | 53 W           |
| Intel Core i5-2430M                                       | 1.18 MH/s                         | 4                 | 35 W           |
| Intel Core i5-3230M                                       | 1.52 MH/s                         | 4                 | 35 W           |
| Intel Core i5-5350U                                       | 1.35 MH/s                         | 4                 | 15 W           |
| Intel Core i5-7200U                                       | 1.62 MH/s                         | 4                 | 15 W           |
| Intel Core i5-8300H                                       | 3.67 MH/s                         | 8                 | 45 W           |
| Intel Core i3-4130                                        | 1.45 MH/s                         | 4                 | 54 W           |
| AMD Ryzen 5 2600                                          | 4.9 MH/s                          | 12                | 65 W           |
| AMD Ryzen R1505G **(fasthash)**                           | 8.5 MH/s                          | 4                 | 35 W           |
| Intel Core i7-11370H **(fasthash)**                       | 17.3 MH/s                         | 8                 | 35 W           |
| Realtek RTD1295                                           | 490 kH/s                          | 4                 | -              |
| Realtek RTD1295 **(fasthash)**                            | 3.89 MH/s                         | 4                 | -              |

</details>

## Community-made softwares

### Please note that these softwares are not developed by us and we do not give any guarantees that use of them will not result in an account getting banned if they get changed in the future.

  ### Miners made by the Duino-Coin community:
  *   [Dockerized Duino-Coin Miner](https://github.com/simeononsecurity/docker-duino-coin) - A Dockerized version of the Duino-Coin Miner by simeononsecurity
  *   :point_right: [**RP2040-HAT-MINING-C**](https://github.com/Wiznet/RP2040-HAT-MINING-C) - **WIZnet RP2040 mining stack**
  *   [DuinoCoinEthernetMiner](https://github.com/Pumafron/DuinoCoinEthernetMiner) - Arduino Ethernet shield Miner by Pumafron
  *   [STM8 DUCO Miner](https://github.com/BBS215/STM8_DUCO_miner) - STM8S firmware for mining DUCO by BBS215
  *   [DuinoCoinbyLabVIEW](https://github.com/ericddm/DuinoCoinbyLabVIEW) - miner for LabVIEW family by ericddm
  *   [Duino-JS](https://github.com/Hoiboy19/Duino-JS) - a JavaScript miner which you can easily implement in your site by Hoiboy19
  *   [Duinotize](https://github.com/mobilegmYT/Duinotize) - Duino website monetizer by mobilegmYT
  *   [hauchel's duco-related stuff repository](https://github.com/hauchel/duco/) - Collection of various codes for mining DUCO on other microcontrollers
  *   [duino-coin-php-miner](https://github.com/ricardofiorani/duino-coin-php-miner) Dockerized Miner in PHP by ricardofiorani
  *   [duino-coin-kodi](https://github.com/SandUhrGucker/duino-coin-kodi) - Mining addon for Kodi Media Center by SandUhrGucker
  *   [MineCryptoOnWifiRouter](https://github.com/BastelPichi/MineCryptoOnWifiRouter) - Python script to mine Duino-Coin on routers by BastelPichi
  *   [Duino-Coin_Android_Cluster Miner](https://github.com/DoctorEenot/DuinoCoin_android_cluster) - mine with less connections on multiple devices by DoctorEenot
  *   [ESPython DUCO Miner](https://github.com/fabiopolancoe/ESPython-DUCO-Miner) - MicroPython miner for ESP boards by fabiopolancoe
  *   [DUCO Miner for Nintendo 3DS](https://github.com/BunkerInnovations/duco-3ds) - Python miner for Nintendo 3DS by PhereloHD & HGEpro
  *   [Dockerized DUCO Miner](https://github.com/Alicia426/Dockerized_DUCO_Miner_minimal) - Miner in Docker by Alicia426
  *   [NodeJS-DuinoCoin-Miner](https://github.com/LDarki/NodeJS-DuinoCoin-Miner/) - simple NodeJS miner by LDarki
  *   [d-cpuminer](https://github.com/phantom32-0/d-cpuminer) - pure C miner by phantom32 & revoxhere
  *   [Go Miner](https://github.com/yippiez/go-miner) by yippiez
  *   [ducominer](https://github.com/its5Q/ducominer) by its5Q
  *   [Unofficial miners directory](https://github.com/revoxhere/duino-coin/tree/master/Unofficial%20miners)
      *   [Julia Miner](https://github.com/revoxhere/duino-coin/blob/master/Unofficial%20miners/Julia_Miner.jl) by revoxhere
      *   [Ruby Miner](https://github.com/revoxhere/duino-coin/blob/master/Unofficial%20miners/Ruby_Miner.rb) by revoxhere
      *   [Minimal Python Miner (DUCO-S1)](https://github.com/revoxhere/duino-coin/blob/master/Unofficial%20miners/Minimal_PC_Miner.py) by revoxhere
      *   [Teensy 4.1 code for Arduino IDE](https://github.com/revoxhere/duino-coin/blob/master/Unofficial%20miners/Teensy_code/Teensy_code.ino) by joaquinbvw

  ### Other tools:
  *   [**Duinogotchi**](https://github.com/OSRdesign/duinogotchi) - Duino-Coin virtual pet project by OSRdesign
  *   [Duino Miner](https://github.com/g7ltt/Duino-Miner) - Arduino Nano based DUCO miner files and documentation by g7ltt
  *   [DUINO Mining Rig](https://repalmakershop.com/pages/duino-mining-rig) - 3D files, PCB designs and instructions for creating your own Duino rig by ReP_AL
  *   [DuinoCoin-balance-Home-Assistant](https://github.com/NL647/DuinoCoin-balance-Home-Assistant) - addon for home assistant displaying your balance by NL647
  *   [ducopanel](https://github.com/ponsato/ducopanel) - a GUI app for controling your Duino-Coin miners by ponsato
  *   [Duino AVR Monitor](https://www.microsoft.com/store/apps/9NJ7HPFSR9V5) - GUI Windows App for monitoring AVR devices mining DUCO by niknak
  *   [Duino-Coin Arduino library](https://github.com/ricaun/arduino-DuinoCoin) by ricaun
  *   [DuinoCoinI2C](https://github.com/ricaun/DuinoCoinI2C) - Use ESP8266/ESP32 as a master for Arduinos by ricaun
  *   [duco-miners](https://github.com/dansinclair25/duco-miners) CLI mining dashboard made by dansinclair25
  *   [Duco-Coin Symbol Icon ttf](https://github.com/SandUhrGucker/Duco-Coin-Symbol-Icon-ttf-.h) by SandUhrGucker
  *   [DUCO Monitor](https://siunus.github.io/duco-monitor/) account statistics website by siunus
  *   [Duino Stats](https://github.com/Bilaboz/duino-stats) official Discord bot by Bilaboz
  *   [DuCoWallet](https://github.com/viktor02/DuCoWallet) GUI Wallet by viktor02
  *   [Duco-widget-ios](https://github.com/naphob/duco-widget-ios) - a Duino-Coin iOS widget by Naphob 
  *   [Duino Lookup](https://axorax.github.io/duino-lookup/) by axorax
  *   [Duino Miner Hassio Add-on](https://github.com/mavotronik/hassio-addons/tree/main/duino_miner_hassio_addon) by mavotronik
  *   [Home Assistant sensors package](https://github.com/mavotronik/Duinocoin_homeassistant) by mavotronik
  *   [ESPGUITOOL](https://github.com/CGameDev/ESPGUITOOL) by kazutokirigaya

 You may also view a similar list on the [website](https://duinocoin.com/apps).


## License

Duino-Coin is mostly distributed under the MIT License. See the `LICENSE` file for more information.<br>
Some third-party included files may have different licenses - please check their `LICENSE` statements (usually at the top of the source code files).


## Terms of service
Our terms of service is available here: <a href="https://duinocoin.com/terms">duinocoin.com/terms</a><br/>


## Privacy policy
Our privacy policy is available here: <a href="https://duinocoin.com/privacy">duinocoin.com/privacy</a><br/>

## Disclaimer
Our disclaimer is available here: <a href="https://duinocoin.com/disclaimer">duinocoin.com/disclaimer</a><br/>


## Active project maintainers

Originally created and maintained by [@revoxhere](https://github.com/revoxhere).<br>
Big thanks to all the [contributors](https://github.com/revoxhere/duino-coin/graphs/contributors) that helped to develop the Duino-Coin project.<br>
Visit [duinocoin.com/team](https://duinocoin.com/team.html) to view more information about the Duino Team.

<hr>

Established August 2019 <br>
Project Link: [https://github.com/revoxhere/duino-coin/](https://github.com/revoxhere/duino-coin/) <br>
Website Link: [https://duinocoin.com/](https://duinocoin.com/) <br>
Duino-Coin Status Page: [https://status.duinocoin.com](https://status.duinocoin.com)

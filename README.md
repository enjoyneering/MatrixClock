[![license-badge][]][license] ![version] [![stars][]][stargazers] ![hit-count] [![github-issues][]][issues]

# MatrixClock
This is an NTP clock built on an ESP8266 & **_five_** MAX7219 or MAX7221 connected in series.

![alt text][ntp_config_page_image]

- Download **Flash Download Tools** from https://www.espressif.com/en/support/download/other-tools
- Download MatrixClock *.bin files
- In Flash Download Tools:
    - set SPI speed **80MHz**
    - set SPI Mode **QIO**
    - set Flash Size **32Mbit**
    - check **DoNotChgBin**
    - **fw_latest.bin** at address **0x00000**
    - **fs_latest.bin** at address **0x200000**
- Connect any ESP8266 with **QIO 4MB** flash to USB, select COM port & baud rate than press **Start**

![alt text][flash_download_tools_image]

- Connect **_five_** MAX7219 or MAX7221 as follows:
    - GPIO13/D7 to DIN/MOSI
    - GPIO14/D5 to CLK/SCLK
    - GPIO15/D8 to CS (can be changed via the WEB interface after)
    - Vcc to +4.0v..+5.0v
    - Gnd to Gnd
    - recommend changing the resistor R1 from 10K to 59K (for 2.5V/10mA LEDs) or to 25K (for 2.5V/20mA LEDs)
- Connect DFPlayer Mini as follows:
    - GPIO5/D1 to RX
    - GPIO4/D2 to TX
    - Vcc to +3.2v..+5.0v
    - Gnd to Gnd
    - 2W/4ohm speaker to SPK1 & SPK2
    - put files from **mp3_sd_root** folder to SD card, up to 36GB formatted as FAT16 or FAT32
    - if you hear loud noise, add a 1K resistor between GPIO4/D2 and TX pins
    - recommended to set the jumper to the STBY-> BUSY position

![alt text][matrixclock_schematic]

- Connect to **MatrixClock** WiFi access point
- Type in browser http://192.168.4.1/
- Put **User Name**: _admin_ & **Password**: _12345678_
- For security purposes, please change login password, go to **Settings -> Server Config** page then click **Save**
- If MatrixClock screen doesn't blink 5 times & doesn't show time go to **Matrix Driver Config** page & rearrange
  **CS pin** according to your schematic then click **Save** & **Reboot**. Make sure GPIO13/D7 connected to DIN/MOSI & GPIO14/D5 to CLK/SCLK 
- Set WiFi Network name & password in **Settings -> Station Config** page than click **Save** & **Reboot**
- The MatrixClock will connect to the WiFi network & Matrix Clock access point will disappear
- Type in browser http://matrixclock.local/ (use IP address instead of mDNS on Android & Win7 devices, address can be found in the uart logs)
- Go to Time or **Settings -> NTP Config** & set your timezone than click **Save** & **Reboot**
- Get free API key from [OpenWeatherMap] & put it in corresponding field on **Settings -> Weather Config** page,
  set other filds than click **Save** & **Reboot**. Matrix Clock now updates the current weather every 2.5 minutes and shows the weather icon and temperature for 5 seconds every 10 seconds.

![alt text][matrixclock_image]

[license-badge]: https://img.shields.io/badge/License-CC%20BY--NC--ND%202.0-lightgrey.svg
[license]:       https://creativecommons.org/licenses/by-nc-sa/4.0/
[version]:       https://img.shields.io/badge/Version-2.0.1-green.svg
[stars]:         https://img.shields.io/github/stars/enjoyneering/MatrixClock.svg
[stargazers]:    https://github.com/enjoyneering/MatrixClock/stargazers
[hit-count]:     https://hits.seeyoufarm.com/api/count/incr/badge.svg?url=https%3A%2F%2Fgithub.com%2Fenjoyneering%2FMatrixClock&count_bg=%2379C83D&title_bg=%23555555&icon=&icon_color=%23E7E7E7&title=hits&edge_flat=false
[github-issues]: https://img.shields.io/github/issues/enjoyneering/MatrixClock.svg
[issues]:        https://github.com/enjoyneering/MatrixClock/issues/

[ntp_config_page_image]:      https://github.com/enjoyneering/MatrixClock/blob/main/images/ntp_config_page.png
[flash_download_tools_image]: https://github.com/enjoyneering/MatrixClock/blob/main/images/flash_download_tool.png
[matrixclock_image]:          https://github.com/enjoyneering/MatrixClock/blob/main/images/matrixclock.jpg
[matrixclock_schematic]:      https://github.com/enjoyneering/MatrixClock/blob/main/images/matrixclock_schematic.png
[OpenWeatherMap]:             https://home.openweathermap.org/users/sign_up

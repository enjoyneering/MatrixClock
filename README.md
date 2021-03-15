[![license-badge][]][license] ![version] [![stars][]][stargazers] [![hit-count][]][count] [![github-issues][]][issues]

# MatrixClock
This is an NTP clock built on an ESP8266 & **_five_** MAX7219 or AS1106 connected in series. Work is in progress & some functions may not work.

![alt text][ntp_config_page_image]

- Download Flash Download Tools from https://www.espressif.com/en/support/download/other-tools
- Download MatrixClock *.bin files
- In Flash Download Tools set SPI speed **80MHz**, SPI Mode **QIO**, Flash Size **32Mbit**
    - **fw_latest.bin** at address **0x00000**
    - **fs_latest.bin** at address **0x200000**
    - connect ESP8266 with 4MB flash to USB, select COM port & speed than press Start

![alt text][flash_download_tools_image]

- Connect **_five_** MAX7219 or AS1106 as follows:
    - GPIO13/D7 to DIN/MOSI
    - GPIO14/D5 to CLK/SCLK
    - GPIO2/D4 to CS (can be changed via the WEB interface after)
- Connect to **MatrixClock** WiFi access point
- Type in browser http://192.168.4.1/
- Put **User Name**: _admin_ & **Password**: _12345678_
- For security purposes, please change login password, go to **Settings -> Server Config** page then click **Save**
- If MatrixClock screen doesn't blink 5 times & doesn't show time go to **Matrix Driver Config** page & rearrange
  **CS pin** according to your schematic then click **Save** & **Reboot**. Make sure GPIO13/D7 connected to DIN (MOSI) & GPIO14/D5 to (CLK) SCLK 
- Set WiFi Network name & password in **Settings -> Station Config** page than click **Save** & **Reboot**
- The MatrixClock will connect to the WiFi network & Matrix Clock access point will disappear
- Type in browser http://matrixclock.local/
- Go to Time or **Settings -> NTP Config** & set your timezone than click **Save** & **Reboot**
- Get free API key from [OpenWeatherMap] & put it in corresponding field on **Settings -> Weather Config** page,
  set other filds than click **Save** & **Reboot**. Matrix Clock now updates the current weather every 2.5 minutes and shows the weather icon and temperature for 5 seconds every 10 seconds.

![alt text][matrixclock_image]

[license-badge]: https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg
[license]:       https://creativecommons.org/licenses/by-nc-sa/4.0/
[version]:       https://img.shields.io/badge/Version-1.0.0-green.svg
[stars]:         https://img.shields.io/github/stars/enjoyneering/MatrixClock.svg
[stargazers]:    https://github.com/enjoyneering/MatrixClock/stargazers
[hit-count]:     http://hits.dwyl.io/enjoyneering/MatrixClock.svg
[count]:         http://hits.dwyl.io/enjoyneering/MatrixClock/badges
[github-issues]: https://img.shields.io/github/issues/enjoyneering/MatrixClock.svg
[issues]:        https://github.com/enjoyneering/MatrixClock/issues/

[ntp_config_page_image]:      https://github.com/enjoyneering/MatrixClock/blob/main/images/ntp_config_page.png
[flash_download_tools_image]: https://github.com/enjoyneering/MatrixClock/blob/main/images/flash_download_tool.png
[matrixclock_image]:          https://github.com/enjoyneering/MatrixClock/blob/main/images/matrixclock.jpg
[OpenWeatherMap]:             https://home.openweathermap.org/users/sign_up

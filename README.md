## Introduction

A headless program designed to automate the process of booking Carleton Library rooms.

The inspiration for this project comes from the tiresome process of needing to book a room nearly every day. This program simply automates the entire process.


https://github.com/HenryZhangxiao/Carleton-Library-Autobooking/assets/44578113/6492b2f0-7124-4779-89d9-ceb51ee8fe7c

![image](https://github.com/HenryZhangxiao/Carleton-Library-Autobooking/assets/44578113/c8d2dee2-45f9-4389-addb-d882f46eb5b0)

<br><br>
#### Table of Contents
- [Technologies Used ](#technologies)
- [How to Run ](#run)
- [Notes ](#notes)


<br></br>
## Technologies Used <a name="technologies"></a>
- Python3
- Selenium
- WebDriver
- ChromeDriver
- discordwebhook
- webdriver-auto-update
- Git


<br></br>
## How to Run <a name="run"></a>
- Download the newest release from [here](https://github.com/HenryZhangxiao/Carleton-Library-Autobooking/releases)
  - It's not recommended to directly clone any branch as there may be unfinished work, etc.
- Pre-requisites
  - python3
  - `pip3 install -r requirements.txt`
    - This project contains an optional Discord Webhook to post room bookings to a private server. To use your own webhook, just modify the `DISCORD_WEBHOOK` definition in `credentials.py` to your own url
  - Google Chrome
    - The Windows, Linux, and MacOS ChromeDrivers can be found in drivers/ and should auto update upon script runtime but if anything fails you can download the compatible ChromeDriver for your arch from https://chromedriver.chromium.org/downloads
    - If the script fails to run it's possible your Chrome version is out of date. Make sure the chrome version is at least the ChromeDriver version or newer
  - It's recommended that you run both Google Chrome and the ChromeDriver executable for your arch at least once before using this script
  - Update the `name` and `email` for your booking in credentials.py keeping it as a string
    - If you don't wish to hardcode your credentials, you can pass them in as command line arguments with `-n NAME -e EMAIL`
- To run Autobook.py
  - `python3 Autobook.py -d [DATE] -r [ROOM_NUMBER] -t [TIME]`
  - You can run `python3 Autobook.py -h` to print the usages for a more detailed explanation of the flags
  - You can optionally use the `--duration` flag to specify a booking duration
  - You can optionally use the `--headless` flag to run the program headlessly
  - If you input a weekday like `Monday`, the script will attempt to book for next `Monday`.
  - If you input a specific date like `Nov 23`, the script will book that exact day.
  - An example command if you were trying to book room 570 at 10:00 AM for next Monday:
    - `python3 Autobook.py -d monday -r 570 -t 1000 --headless`


<br></br>
## Notes <a name="notes"></a>
- This script has a dedicated [Discord bot](https://github.com/HenryZhangxiao/Carleton-Library-Autobooking-Bot) to run this script at will with 24/7 uptime

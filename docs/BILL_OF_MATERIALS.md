# Stanford Augmented Cane: Bill of Materials (reference)

[Back to main README](../README.md) | [Build Checklist](CHECKLIST.md)

This is the parts list from Stanford's open-source Augmented Cane, copied out of their `Bill of Materials.xlsx` so we can look at it without opening the spreadsheet. We are using it as a reference for our GDG lidar cane project. We are not building this exact list.

- Original Source repo: https://github.com/pslade2/AugmentedCane
- Paper: Slade, Tambe, Kochenderfer, "Multimodal sensing and intuitive steering assistance improve navigation and mobility for people with impaired vision", Science Robotics, 2021. https://www.science.org/doi/10.1126/scirobotics.abg6594
- Build instructions: `cane_assembly.pdf` in the repo root

**Total: $430.34 at 2021 prices** for 22 line items (23 parts, since the mounting hub is x2). Note that shipping is listed as $0 on every row.

Quick heads up for Michael: these prices are from around January 2021. Raspberry Pi boards in particular cost a lot more now, and some of these exact products may be discontinued, so we may have to look for alternatives.

## Our parts list

What we actually need for an obstacle-detection-only cane (no GPS, no wheel, no camera). Item numbers match Stanford's list below. Prices are Stanford's 2021 prices except our lidar.

| #   | Part                                          | Cost        |
| --- | --------------------------------------------- | ----------- |
| 1   | Raspberry Pi 4B (4 GB)                        | $55.00      |
| 2   | Our lidar (TF-Luna), replaces the RPLidar A1  | $24.99      |
| 5   | NXP IMU                                       | $14.95      |
| 8   | Pi Cobbler Breakout                           | $6.95       |
| 9   | Protohat                                      | $4.95       |
| 11  | Micro SD Card                                 | $6.90       |
| 14  | USB cable                                     | $2.95       |
| 15  | Rechargeable batteries (power the Pi)         | $12.50      |
| 18  | Pi Case                                       | $18.99      |
| 19  | White Cane (might 3D print)                   | $17.00      |
|     | **Total**                                     | **$165.18** |

The IMU (#5) is optional for the first build. Without it the total is $150.23.

Still to add (not on Stanford's list, since they used the wheel for feedback):

- 1 or 2 coin vibration motors
- Motor driver board, or a transistor + diode, to run the motor from the Pi

## Stanford's full parts list

The "What it's for" column is our own note, not from the spreadsheet.

| #   | Part                                                                                                 | Vendor    | Qty | Unit cost | Total       | What it's for                                    |
| --- | ---------------------------------------------------------------------------------------------------- | --------- | --- | --------- | ----------- | ------------------------------------------------ |
| 1   | [Raspberry Pi 4B (4 GB)](https://www.adafruit.com/product/4296)                                      | Adafruit  | 1   | $55.00    | $55.00      | Main computer                                    |
| 2   | [RPLidar A1](https://www.amazon.com/dp/B07TJW5SXF)                                                   | Amazon    | 1   | $99.99    | $99.99      | 360 degree scanning lidar for obstacle detection |
| 3   | [Motor](https://www.pololu.com/product/3225)                                                         | Pololu    | 1   | $19.95    | $19.95      | Drives the omniwheel at the cane tip             |
| 4   | [GPS Breakout](https://www.adafruit.com/product/746)                                                 | Adafruit  | 1   | $39.95    | $39.95      | Outdoor position for navigation                  |
| 5   | [NXP IMU](https://www.adafruit.com/product/3463)                                                     | Adafruit  | 1   | $14.95    | $14.95      | Orientation and motion of the cane               |
| 6   | [RPi Camera](https://www.adafruit.com/product/3099)                                                  | Adafruit  | 1   | $29.95    | $29.95      | Object recognition                               |
| 7   | [RPi Camera Cable](https://www.adafruit.com/product/1731)                                            | Adafruit  | 1   | $2.95     | $2.95       | Connects camera to Pi                            |
| 8   | [Pi Cobbler Breakout](https://www.adafruit.com/product/1754)                                         | Adafruit  | 1   | $6.95     | $6.95       | Breaks out the Pi's GPIO pins                    |
| 9   | [Protohat](https://www.adafruit.com/product/2310)                                                    | Adafruit  | 1   | $4.95     | $4.95       | Solderable board that sits on the Pi             |
| 10  | [GPS Antenna](https://www.adafruit.com/product/960)                                                  | Adafruit  | 1   | $14.95    | $14.95      | Better GPS reception                             |
| 11  | [Micro SD Card](https://www.amazon.com/dp/B073K14CVB)                                                | Amazon    | 1   | $6.90     | $6.90       | Pi storage                                       |
| 12  | [LiPo Battery](https://www.amazon.com/dp/B072PPRPRN)                                                 | Amazon    | 1   | $13.00    | $13.00      | Power (likely for the motor)                     |
| 13  | [LiPo Charger](https://www.amazon.com/dp/B072K5LHGM)                                                 | Amazon    | 1   | $12.00    | $12.00      | Charges the LiPo                                 |
| 14  | [USB cable](https://www.adafruit.com/product/4472)                                                   | Adafruit  | 1   | $2.95     | $2.95       | Power or data cable                              |
| 15  | [Rechargeable Battery](https://www.amazon.com/dp/B07MS1B8KQ)                                         | Amazon    | 1   | $12.50    | $12.50      | Power (likely for the Pi)                        |
| 17  | [Motor Driver](https://www.adafruit.com/product/3190)                                                | Adafruit  | 1   | $7.50     | $7.50       | Lets the Pi control the motor                    |
| 18  | [Pi Case](https://www.amazon.com/dp/B07VX2WDHM)                                                      | Amazon    | 1   | $18.99    | $18.99      | Case with fan for the Pi                         |
| 19  | [White Cane](https://www.amazon.com/dp/B002VWK0HI)                                                   | Amazon    | 1   | $17.00    | $17.00      | The cane itself                                  |
| 20  | [Ear Buds](https://www.amazon.com/dp/B083Y19JTN)                                                     | Amazon    | 1   | $16.00    | $16.00      | Bluetooth audio feedback                         |
| 21  | [4mm shaft](https://www.amazon.com/dp/B07FYTQWDC)                                                    | Amazon    | 1   | $7.99     | $7.99       | Axle for the omniwheel                           |
| 22  | [Omniwheel](https://www.robotshop.com/en/60mm-aluminum-omni-wheel.html)                              | Robotshop | 1   | $13.50    | $13.50      | Tip wheel that steers the user                   |
| 23  | [Aluminum mounting hub](https://www.robotshop.com/en/4mm-aluminum-mounting-hub-60mm-omni-wheel.html) | Robotshop | 2   | $6.21     | $12.42      | Attaches the wheel to the shaft                  |
|     |                                                                                                      |           |     | **Total** | **$430.34** |                                                  |

There is no item 16 in the original spreadsheet. The numbering skips from 15 to 17.

## Cost by group

Again note: this is what it cost 5 years ago, unfortunately our papa Jensen has made it all expensive now :(

| Group                                               | Parts             | Cost    |
| --------------------------------------------------- | ----------------- | ------- |
| Sensing (lidar, camera + cable, GPS + antenna, IMU) | 2, 4, 5, 6, 7, 10 | $202.74 |
| Computer (Pi, SD card, case, cobbler, protohat)     | 1, 8, 9, 11, 18   | $92.79  |
| Steering (motor, driver, omniwheel, shaft, hubs)    | 3, 17, 21, 22, 23 | $61.36  |
| Power (batteries, charger, USB cable)               | 12, 13, 14, 15    | $40.45  |
| Cane and audio (white cane, ear buds)               | 19, 20            | $33.00  |

Almost half the budget is sensing, and the RPLidar alone is about a quarter of the total.

## How this compares to our plan

Our cane only detects obstacles ahead. We are not doing GPS navigation, steering, or object recognition, so the GPS, camera and the whole steering group are dropped (about $150 of the list above).

| Stanford                              | Our plan                                      | Why                                                          |
| ------------------------------------- | --------------------------------------------- | ------------------------------------------------------------ |
| RPLidar A1, $99.99, scans 360 degrees | TF-Luna, $24.99, single point                 | We only need "something is ahead" at first                   |
| Raspberry Pi 4B 4GB                   | Same, Raspberry Pi 4B 4GB                     | Pi Zero 2 W or ESP32 would be cheaper if budget is tight     |
| White cane, $17                       | White cane, might 3D print                    | Could save money and fit our housing better                  |
| Motorized omniwheel steering, $61     | Dropped. Normal cane tip, vibration in handle | The wheel only exists to steer the user; we just warn them   |
| Ear buds for audio                    | Vibration first, audio later                  | Users need their hearing for traffic and echoes              |
| GPS + antenna, $54.90                 | Dropped                                       | No navigation, obstacle detection only                       |
| Camera + cable, $32.90                | Dropped                                       | No object recognition                                        |
| IMU                                   | IMU (MPU6050 or BNO055), stage 2              | Cane tilt to filter false alerts, fall detection             |
| LiPo plus separate battery            | Rechargeable batteries for the Pi only        | No motor to power, so no LiPo or LiPo charger                |

# Build Checklist

Step by step plan build by our other teammate "papa claude"

One thing I'd reccomend for the project, is to get each piece working on its own before connecting it to the next one, also since we have never worked on an engeeniering project before and we wire everything at once, nobody can tell which part is broken.

## Phase 0: Setup and decisions

- [ ] Everyone reads Stanford's `cane_assembly.pdf` and the [bill of materials](BILL_OF_MATERIALS.md) in the README
- [ ] Agree on the stage 1 goal: cane vibrates harder as an obstacle gets closer. Nothing else yet
- [ ] Decide feedback type: vibration, speaker, or both (leaning vibration, since users need their hearing for traffic and echoes)
- [ ] Decide the board: Pi Zero 2 W, or ESP32
- [ ] Assign roles: hardware and wiring / CAD (Onshape) / sensor code / companion app
- [ ] Confirm club budget

## Phase 1: First order (about $55 to $70)

- [ ] TF-Luna lidar, _This is a single-point lidar we chose (one dot straight ahead), not a 2D scanner like Stanford's RPLidar A1, we should choose 2D scanner imo, but for testing it's cheap and it's fine for prototyping_
- [ ] Raspberry Pi Zero 2 W (with headers) or the board we picked
- [ ] microSD card, 16 GB or bigger
- [ ] 2 coin vibration motors
- [ ] Motor driver board (or a transistor + diode if someone knows how to wire that)
- [ ] Breadboard and jumper wires
- [ ] USB power supply or cable for the Pi

## Phase 2: Lidar prints distance (first milestone)

- [ ] Flash Raspberry Pi OS Lite to the SD card with Raspberry Pi Imager, set WiFi and enable SSH in the imager settings
- [ ] SSH into the Pi from a laptop
- [ ] Run `sudo raspi-config` > Interface Options > Serial Port: login shell **No**, serial hardware **Yes**, then reboot
- [ ] Install pyserial on the Pi with: `sudo apt install python3-serial`. We gotta figure out the Pi setup first, I'd reserve a meeting personally just for this.
- [ ] Wire the TF-Luna. _claude really wants you to know that you should power off while wiring, unless you want that KABOOM, in which case go ahead_

> this is for our engeenering students, miachel you are leading this haha

| TF-Luna pin | Pi pin              |
| ----------- | ------------------- |
| 1 (5V)      | Pin 2 (5V)          |
| 2 (RXD)     | Pin 8 (GPIO14, TX)  |
| 3 (TXD)     | Pin 10 (GPIO15, RX) |
| 4 (GND)     | Pin 6 (GND)         |

- [ ] Write `lidar.py` that reads the sensor on `/dev/serial0` at 115200 baud and prints distance in cm
- [ ] Wave a hand in front of it and confirm the numbers change
- [ ] Commit the script and a photo of the wiring to the repo

If nothing prints: TX and RX are probably swapped, or the serial port isn't enabled.

> this is our checkpoint, after this it's all housing, soldering and walk testing. that should be more fun than all this setup :p

## Phase 3: Vibration feedback

- [ ] Wire one vibration motor through the driver board to a GPIO pin (never straight to a GPIO pin, it draws too much current)
- [ ] Write a test script that buzzes the motor on and off
- [ ] Combine with the lidar: closer object = stronger or faster pulses
- [ ] Add a moving average so the buzz doesn't jitter
- [ ] Ignore readings with low signal strength (under about 100)
- [ ] Pick the distance thresholds (starting guess: start buzzing at 2 m, strongest under 0.5 m)

## Phase 4: Bench testing

- [ ] Test against a wall, a chair, a person, a pole
- [ ] Test against glass and dark surfaces
- [ ] Test outside in direct sunlight
- [ ] Write down where it fails in `docs/test-notes.md`
- [ ] Measure how long it runs on battery

## Phase 5: Second order (about $60 to $80)

- [ ] Folding white cane
- [ ] Second distance sensor (VL53L1X) for head-height obstacles
- [ ] IMU (MPU6050 or BNO055)
- [ ] Slim USB power bank
- [ ] Protoboard, power switch, heat shrink, solder

## Phase 6: Make it a cane

- [ ] Measure the cane diameter and all the parts
- [ ] Design a clip-on housing in Onshape (look at Stanford's `cane_hull.stl` for ideas)
- [ ] Print it at the SMCL makerspace. Expect 2 or 3 reprints
- [ ] Add the upward-angled sensor with a different vibration pattern than "ahead"
- [ ] Add the IMU and read the cane's tilt
- [ ] Solder everything onto protoboard
- [ ] Mount it all on the cane, with the vibration motor in the handle
- [ ] Make the script start automatically on boot (systemd service)
- [ ] Add a power switch and a low battery warning

## Phase 7: Walk testing

- [ ] Walk test indoors with eyes closed, always with a spotter next to the tester
- [ ] Walk test outdoors on campus, with a spotter
- [ ] Tune thresholds and vibration patterns from what we learn
- [ ] Contact CSM's disability resource office or a local blind services center
- [ ] Get feedback from real cane users before adding more features
- [ ] Write up what they said in `docs/user-feedback.md`

Safety: this is an add-on to a white cane, not a replacement. Nobody should rely on the prototype alone while we're testing.

## Phase 8: Stage 2 features (pick 1 or 2 based on feedback)

- [ ] Drop-off detection for curbs and stairs (downward sensor)
- [ ] Fall detection with SOS text (IMU + phone)
- [ ] Find my cane (beeps when called from the phone)
- [ ] Companion web app over Web Bluetooth: settings, battery level
- [ ] "What's in front of me?" button (needs Pi 5 + camera)
- [ ] GPS navigation
- [ ] Upgrade to a scanning lidar like Stanford's RPLidar A1

## Phase 9: Document and show

- [ ] Wiring diagram in the repo
- [ ] Our own bill of materials with real prices paid
- [ ] Setup instructions so someone else can rebuild it
- [ ] Photos and a short demo video
- [ ] Credit Stanford's Augmented Cane paper in the README
- [ ] Present at a GDG meeting

# Lidar Cane (GDG on Campus, College of San Mateo)

Our club project: a low-cost lidar cane that warns visually impaired users about obstacles in front of them, based on Stanford's open-source Augmented Cane.

## Scope

The cane does one job: tell the user when something is in front of them, by vibrating in the handle (stronger or faster as the obstacle gets closer).

We are **not** building:

- GPS or route navigation
- The motorized wheel at the cane tip (Stanford uses it to steer the user; we use vibration instead and keep a normal white cane tip)
- Camera or object recognition

Final design: white cane + distance sensor + small board (Pi Zero 2 W or ESP32) + vibration motor + USB power bank.

Right now we are at the idea stage. The first goal is simple: a Raspberry Pi reads a lidar sensor and prints the distance, then we add feedback (vibration or sound) on top of that.

## Docs

- [Bill of Materials](docs/BILL_OF_MATERIALS.md): Stanford's original parts list with prices, and how our plan differs
- [Build Checklist](docs/CHECKLIST.md): step by step plan, tick things off as we go

## Reference

- Original repo: https://github.com/pslade2/AugmentedCane
- Paper: https://www.science.org/doi/10.1126/scirobotics.abg6594
- Build instructions: `cane_assembly.pdf` in this repo
- Cane housing 3D models: `cane_hull.stl` / `cane_hull.stp`
- Stanford's code: `obstacle_avoidance.py`, `gps_navigation.py`, `hallway_virtual_shorelining.py`, `haptic_test.py`, `cane_functions.py`

Their code is written for an RPLidar A1 and a motorized wheel, so we use it as a reference and adapt ideas from it. It won't run on our hardware as is. Only the "read the lidar and decide if something is close" part of `obstacle_avoidance.py` is relevant to us; `gps_navigation.py`, `hallway_virtual_shorelining.py` and the wheel steering code are out of scope.

## Credit

This is a fork of the Stanford Augmented Cane project.

> note from the original repo.

_[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5195090.svg)](https://doi.org/10.5281/zenodo.5195090)_

_The Augmented Cane project improves the mobility of people with impaired vision by using cutting-edge robotics. Read the full research paper: https://www.science.org/doi/10.1126/scirobotics.abg6594_

_If you use a part of this project please cite our work: P. Slade, A. Tambe, M. J. Kochenderfer, Multimodal sensing and intuitive steering assistance improve navigation and mobility for people with impaired vision. Sci. Robot. 6, eabg6594 (2021)._

_The Augmented Cane project is completely open-source. To build your own copy check out the cane_assembly document with instructions on replicating the device. The image of the Raspberry Pi used is available in a separate repository due to its size: https://doi.org/10.5281/zenodo.5508346_

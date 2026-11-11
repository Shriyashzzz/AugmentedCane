# Lidar Cane (GDG on Campus, College of San Mateo)

Our club project: a low-cost lidar cane for visually impaired navigation, based on Stanford's open-source Augmented Cane.

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

Their code is written for an RPLidar A1 and a motorized wheel, so we use it as a reference and adapt ideas from it. It won't run on our hardware as is.

## Credit

This is a fork of the Stanford Augmented Cane project.

> note from the original repo.

_[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.5195090.svg)](https://doi.org/10.5281/zenodo.5195090)_

_The Augmented Cane project improves the mobility of people with impaired vision by using cutting-edge robotics. Read the full research paper: https://www.science.org/doi/10.1126/scirobotics.abg6594_

_If you use a part of this project please cite our work: P. Slade, A. Tambe, M. J. Kochenderfer, Multimodal sensing and intuitive steering assistance improve navigation and mobility for people with impaired vision. Sci. Robot. 6, eabg6594 (2021)._

_The Augmented Cane project is completely open-source. To build your own copy check out the cane_assembly document with instructions on replicating the device. The image of the Raspberry Pi used is available in a separate repository due to its size: https://doi.org/10.5281/zenodo.5508346_

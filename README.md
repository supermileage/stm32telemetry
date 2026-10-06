# UBC Supermileage Telemetry

## Overview
Used to gather information/sensor data from the vehicle, store it and potential transmit it. This data can then be processed.\
More info: https://app.notion.com/p/Vehicle-Telemetry-System-3ee7e02c955f806296e9d68eaa08e37a \
Info about all projects: https://app.notion.com/p/Software-Embedded-Division-Project-Plan-2026-2027-3bb7e02c955f80a282bec8cfb8830d0f

## Timeline
View on notion

## Quick start (flash a release)
1. Download release (.bin)
2. Connect to the board to your computer via microUSB (STLK CN8 connector)
3. The board will show up as a USB drive, drag the .bin into it. ST-LINK LED should flash, if `FAIL.TXT` is created then it failed

## Project structure
```
/firmware			the main telemetry code
	/Core/Src/main.c
    
/SubProjects 	 	other CubeIDE projects used to support development

/lib/				shared drivers used by firmware and SubProjects
	/README.MD		how to properly include this folder
		
/docs				documentation
```
Each folder has its own README.md if it requires more info

## Versioning and updates
Semantic versioning will be used: `vMAJOR.MINOR.PATCH`
- Major will be incremented when a milestone is hit such as MVP
- Minor will be incremented for new new features/capabilities or breaking change
- Patch will be incremented for bug fixes and minor backward compatible changes

When a new feature like a sensor has been impemented and works well a release should be made. Other signficant achievements should also be released, use judgment. Detail changes (features added or removed, things broken/not backward compatible) in description so it can act as a changelog. \
Any release should begin as a pre-release, if it has been tested on the car and works well it should become a release, a note on what is functioning would also be good.

To see how to make a release please view [release tutorial](release.md)

# Progress and next steps
Makes it easy to see where we are and pickup the next task
- [ ] MVP
	- [ ] Communicate with IMU on the board
	- [ ] MicroSD

# Telemetry (STM32)

## Overview
Used to gather information/sensor data from the vehicle, store it and potential transmit it. This data can then be processed.
More info: https://app.notion.com/p/Vehicle-Telemetry-System-3ee7e02c955f806296e9d68eaa08e37a
Info about all projects: https://app.notion.com/p/Software-Embedded-Division-Project-Plan-2026-2027-3bb7e02c955f80a282bec8cfb8830d0f

## Timeline
View on notion

## Design decisions

- FreeRTOS is being used to ensure data isn't dropped. Different data sources operate at different frequencies so being able to switch to logging that data from another task will ensure it isn't dropped.
    - FreeRTOS was selected specifically due to familiarity and meets requirements
- Heap_1 was selected for the RTOS as dynamic memory allocation does need seem necessary at the moment

## Project structure
```
/firmware/      the main telemetry code
    /Core/Src/main.c
/SubProjects/   other CubeIDE projects used to support development
/docs
```

## Versioning and updates
Semantic versioning will be used: `vMAJOR.MINOR.PATCH`
- Major will be incremented when a milestone is hit such as MVP
- Minor will be incremented for new new features/capabilities
- Patch will be incremented for bug fixes

When a new feature like a sensor has been impemented and works well a release should be made. Other signficant achievements should also be released, use judgment.\
Any code that hasn't been tested on the car should be released as pre-release.\
When releasing code make sure to compile for a release and not debug so it's more optimized. Find the .elf under projectname/Release \
When a release has been tested and is known to be good please state that in the tag for future reference in case we need roll back in a hurry.

Suggestion: when we begin logging put the version and git hash to track where bugs came from

Update the `CHANGELOG.MD` when adding 
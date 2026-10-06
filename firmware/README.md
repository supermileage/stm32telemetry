## Design decisions

- As HAL, CubeMX output and FreeRTOS are all in C and most embedded code is written in C it would be good to continue with it when possible. If C++ will bring large benefits then it can begin being used, especially as it's easy to add.
	- Begin with `struct`s
- FreeRTOS is being used to ensure data isn't dropped. Different data sources operate at different frequencies so being able to switch to logging that data from another task will ensure it isn't dropped.
    - FreeRTOS was selected specifically due to familiarity and meets requirements
- Heap_1 was selected for the RTOS as dynamic memory allocation does need seem necessary at the moment

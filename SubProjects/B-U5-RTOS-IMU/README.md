## Notes

- The board has an in built 3D accelerometer and gyroscope, ISM330DHCX. 
    - It is connected to the second I2C bus, I2C2.
    - The 7 bit address is 1101011
    - After the start condition (ST) a slave address is sent, once a slave acknowledge (SAK) has been
	- returned, an 8-bit sub-address (SUB) is transmitted. The increment of the address is configured by the CTRL3_C (12h) (IF_INC). (default increments after each access)
	- takes 35ms to turn on (table 3)
	- ODR = output data rate
	- ODR_XL[3:0] in CTRL1_XL controls sampling rate or off of accelerometer. View table 43 in datasheet for bit to sampling rate selections. To use high performance bit XL_HM_MODE bit in CTRL6_C should be cleared, default 0.
	- ODR_G[3:0] in CTRL2_G controls sampling rate or off of gyroscope. View table 46 in datasheet for bit to sampling rate selections. To use high performance bit G_HM_MODE bit in CTRL7_G should be cleared, default 0.

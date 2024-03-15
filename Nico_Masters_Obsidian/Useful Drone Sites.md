
# Construction guides and tips

- buzzed/light with built in battery, to retrieve drone, when lost underground
- [LiPo vs. Li-ion (Use LiPo)](https://www.unmannedsystemstechnology.com/feature/lipo-vs-lithium-ion-batteries-for-unmanned-robotics-applications/#:~:text=When%20deciding%20on%20a%20battery,probably%20the%20way%20to%20go.) :
- [Drone Basics](https://oscarliang.com/fpv-drone-guide/#Basic-Drone-Control)
	- Motors:
		- Lower KV ratings for better efficiency
		- Larger LiPo or Li-ion Batteries
	- Propellers:
		- Lower pitch propeller for better efficiency
		- 5" = smaller, 7" more payload and better efficiency
		- Therefore 6" might be optimal? but check availability?
	-  Flight Controller
		- Popular firmware = Betaflight 
			- open-source
			- performs well
			- updated frequently
			- huge selection of flight controllers available
			- added features for long-range flights
	- ESC 
		- Popular firmware = BLHeli_S or BLHeli_32 (99% of FPV's)
		- Firmware: BLHeli_32 Is faster and more future proof
		- Protocol: DShot300 and DShot600 (number is speed of controller)
	- Blackbox: for tuning drone. 
		- records flight data which can be used for tuning PID settings
		- [Tuning parameters](https://oscarliang.com/pid-filter-tuning-blackbox/)
- [Extend drone Time of flight](https://oscarliang.com/improve-fpv-drone-flight-time-efficiency/)
	- Higher C-rating = less voltage sag but, more inefficient, Heavier
	- Li-ion = ~double capacity for same weight, but lower discharge rate
	- Lower pitch propeller for better efficiency
	- 5" = smaller, 7" more payload and better efficiency
	- Properly balance Center of gravity (COG). 4 motors working at same level = higher efficiency
- [Accessory Guide (Chargers, Radio receiver/Remote controller)](https://oscarliang.com/my-tools-gear-quads/)
	- [Build tutorial](https://oscarliang.com/how-to-build-fpv-drone/)
- [Propellers](https://oscarliang.com/propellers/#Propeller-Size)
	- Suggestion: HQ props, triblades = more smoothness
		- For 6":
			- long range and flight time: Gemfan Hurricane 6038-4
			- Speed and racing: HQ DP 6×4.5×3
		- For 5":
			- All rounder:  HQ 5×4.3×3 V2S
			- Durable and cheap: DAL Cyclone 5045C
		- For 7":
			- All rounder: HQ DP 7×3.5×3-v1s
	- Mounting Propellers:
		- 2 CW and 2 CCW
		- CW (R)= left top + right bottom (Betaflight default)
		- CCW (C)= left bottom + right top (Betaflight default)
	- [Components compatibility table](https://oscarliang.com/table-prop-motor-lipo-weight/)
	- Props can produce 20-30% less thrust in air compared to static thrust test
- [5" Drone Parts list](https://oscarliang.com/best-5-inch-fpv-drone-parts/)
- 3D Printing Predesigned parts
	- [Thingiverse](https://www.thingiverse.com/)
	- Very compatible with "Source One" frames
- [Flight Controller Explained: Understanding FPV Drone Control Systems](https://oscarliang.com/flight-controller-explained/)
	- all have gyroscope, accelerometer
	- only some have barometer and compass(magnetometer)(Not necessary)
	- can also serve as hub for  ESC, GPS, LED, servos, radio receiver, FPV cam and VTX
	- Make sure flight controller has soft mount, increases performance
	- Run different Firmware:
		- Popular firmware = Betaflight 
			- open-source
			- performs well
			- updated frequently
			- huge selection of flight controllers available
			- added features for long-range flights
			- lots of resources available online
			- Best Hardware support
			- Best For Beginners
		- Emuflight - Try when Betaflight is not working, runs on same hardware
		- ArduPilot = supports a variety of vehicles, including quadcopters, planes, rovers, ground vehicles, even RC submarines
			- extensive features and customization options
			- good choice for advanced pilots and developers
			- Hardest  Learning Curve
			- Lacks performance optimization
			- Less resources available online
			- Shines in autonomous Flight
		- INAV
			- Good at autonomous flight, after ArduPilot
		- PX4
	- Check Gyro specs. 
		- Avoid or thoroughly research the following:
			- MPU6500
			- MPU9250
			- ICM20689
			- ICM20602
		- Rather try:
			- MPU6000
			- BMI270
-  Microcontroller
	- [Khadas Vim 4 performance](https://www.tomshardware.com/reviews/khadas-vim4-review#:~:text=Power%20and%20Temperature%20Tests%20of%20Khadas%20VIM4&text=When%20under%20load%20for%20our,a%201.02W%20power%20consumption.)
- ESCs 
	- https://neumotors.com/apd-electronic-speed-controls-for-brushless-motors/apd-120f3-brushless-esc-2/
	- https://store.tmotor.com/product/p60a-v2-pacer-esc.html
	- https://shop.iflight.com/electronics-cat27/BLITZ-E55-4-IN-1-2-6S-ESC-Pro1694
	- https://holybro.com/collections/fpv-esc/products/tekko32-f4-4in1-60a-esc
 -  [STM32 Chip Naming Convention](https://oscarliang.com/f1-f3-f4-flight-controller/)
- Batteries:
	- [GENSACE 8000MAH 4S 14.8V BASHING PRO 100C](https://www.rc-king.co.za/4s-lipo-battery/3448-gensace-8000mah-4s-148v-bashing-pro-100c-2621024439904.html)
		- [752g](https://genstattu.com/gens-ace-4s2p-8000mah-100c-14-8v-bashing-pro-g-tech-lipo-battery-pack-with-ec5-plug-for-arrma/)
	- [GENS ACE 5000MAH 14.8V 4S 60C LIPO BATTERY](https://www.rc-king.co.za/4s-lipo-battery/3477-gens-ace-5000mah-148v-4s-60c-lipo-battery-2279512277424.html)
		- [436g](https://denkit.co.za/product/14-8v-4s-5000mah-60c-bashing-battery-with-xt-90-gens-ace/)
	- [GENS ACE 6S 5000MAH 22.2V 45C LIPO](https://www.rc-king.co.za/6s-lipo-battery/2493-gens-ace-6s-5000mah-222v-45c-lipo-2160492958574.html)
	- [GENS ACE 6S 6000MAH 22.2V 45C LIPO BATTERY](https://www.rc-king.co.za/batteries/3456-gens-ace-6s-6000mah-222v-45c-lipo-battery-2069323675317.html)

| Battery | Size (mAh) | Cost (R) | Cell | C-Rating | Mass (g) |
| ---- | ---- | ---- | ---- | ---- | ---- |
| GENSACE 8000MAH 4S 14.8V BASHING PRO 100C | 8000 | 2400 | 4s | 100C | 752 |
| GENS ACE 5000MAH 14.8V 4S 60C LIPO BATTERY | 5000 | 1200 | 4s | 60C | 436 |
| GENS ACE 6S 6000MAH 22.2V 45C LIPO BATTERY | 6000 | 2500 | 6s | 45C | 812 |
| GENS ACE 6S 5000MAH 22.2V 45C LIPO | 5000 | 2085 | 6s | 45C | 713 |
4s = 14.8V
6s = 22.2V



# Useful Drone Info from journal papers (Drone Construction)
- [RMF-Obelix](https://ieeexplore.ieee.org/document/9561999)
	- 


# Useful Drone Info from journal papers (Collision Avoidance)
- Euler spring collision Protection




# Useful Drone Info from journal papers (SLAM)
- A ROS Multi-Tier UAV Localization Module Based on GNSS, Inertial and Visual-Depth Data
	-  ORB_SLAM2  is a highly integrable simultaneous localization and mapping (SLAM) algorithm option, as it can utilize monocular, stereo and/or visual-depth (RGB-D) data.
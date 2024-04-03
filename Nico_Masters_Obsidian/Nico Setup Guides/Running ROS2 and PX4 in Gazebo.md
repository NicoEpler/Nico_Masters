In one terminal run MicroXRCEAgent:
```bash
MicroXRCEAgent udp4 -p 8888
```
In another terminal run QGC:(Only if installed)
```bash
~/QGroundControl.AppImage 
```
In a third terminal start gz_x500 simulated drone:
```bash
cd Desktop/Drone_Simulations/PX4-Autopilot/
make px4_sitl gz_x500
```
```bash
cd
cd Desktop
cd "Drone Simulations"
git clone --depth=1 https://github.com/PX4/PX4-Autopilot.git --recursive
bash ./PX4-Autopilot/Tools/setup/ubuntu.sh
cd PX4-Autopilot/
make px4_sitl gz_x500
```

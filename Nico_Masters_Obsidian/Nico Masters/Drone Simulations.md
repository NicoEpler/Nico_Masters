

# Getting the simulation up and running(ROS2 and PX4 in Gazebo)

- Interesting video that can be followed. Also includes some basic insight into control code. Find video [Here](https://www.youtube.com/watch?v=8gKIP0OqHdQ&ab_channel=ARKElectronics)
- The github link for the resources used in the video can be found [Here](https://github.com/ARK-Electronics/ROS2_PX4_Offboard_Example)


- Also try [this setup](https://github.com/nikhilsnayak3473/ROS2-PX4)




# Changing Simulation Settings/Configurations ([From PX4 Website](https://docs.px4.io/main/en/sim_gazebo_gz/))

1. 
- The simulation can be run inside a particular world by concatenating the desired world to the name of the desired vehicle. For example, to run the windy world with the `x500` vehicle you can specify:

```
make px4_sitl gz_x500_windy
```

- You can also specify the world using the `PX4_GZ_WORLD` environment variable:

```
PX4_GZ_WORLD=windy make px4_sitl gz_x500
```

2. The startup pipeline allows for highly flexible configuration. In particular, it is possible to (Check website):

- Start a new simulation with an arbitrary world or attach to an already running simulation.
- Add a new vehicle to the simulation or link a new PX4 instance to an existing one.

# Adding a Model

To add a new model:

1. Define an [airframe configuration file](https://docs.px4.io/main/en/dev_airframes/adding_a_new_frame.html).
    
2. Define the default parameters for Gazebo in the airframe configuration file (this example is from [x500 quadcopter (opens new window)](https://github.com/PX4/PX4-Autopilot/blob/main/ROMFS/px4fmu_common/init.d-posix/airframes/4001_gz_x500)):
    
    ```
    PX4_SIMULATOR=${PX4_SIMULATOR:=gz}
    PX4_GZ_WORLD=${PX4_GZ_WORLD:=default}
    PX4_SIM_MODEL=${PX4_SIM_MODEL:=<your model name>}
    ```
    
    - `PX4_SIMULATOR=${PX4_SIMULATOR:=gz}` sets the default simulator (Gz) for that specific airframe.
        
    - `PX4_GZ_WORLD=${PX4_GZ_WORLD:=default}` sets the default world for that specific airframe.
        
    - Setting the default value of `PX4_SIM_MODEL` lets you start the simulation with just:
        
        ```
        PX4_SYS_AUTOSTART=<your new airframe id> ./build/px4_sitl_default/bin/px4
        ```
        
3. Add CMake Target for the [airframe (opens new window)](https://github.com/PX4/PX4-Autopilot/blob/main/ROMFS/px4fmu_common/init.d-posix/airframes/CMakeLists.txt).
    
    - If you plan to use "regular" mode, add your model SDF to `Tools/simulation/gz/models/`.
    - If you plan to use _standalone_ mode, add your model SDF to `~/.simulation-gazebo/models/`
    
    You can of course also use both.









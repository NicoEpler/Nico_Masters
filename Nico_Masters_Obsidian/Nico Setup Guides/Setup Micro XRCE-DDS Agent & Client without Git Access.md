- Clone "Fast-DDS" folder from "https://github.com/eProsima/Fast-DDS.git" using other PC
- Paste Cloned "Fast-DDS" folder into "/home/nico/Desktop/Drone_Simulations" and rename folder to Fastdds
- Replace code in "fastdds-gitclone.cmake" file in "/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/tmp" location with the following code:

```bash
if(NOT EXISTS "/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds-stamp/fastdds-gitinfo.txt")
  message(FATAL_ERROR "Repository not found at specified location.")
endif()

# Specify the destination of the repository on your device
set(repository_destination "/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds")

# Check if the repository has been updated
if(NOT "/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds-stamp/fastdds-gitinfo.txt" IS_NEWER_THAN "/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds-stamp/fastdds-gitclone-lastrun.txt")
  message(STATUS "Avoiding repeated copy, stamp file is up to date: '/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds-stamp/fastdds-gitclone-lastrun.txt'")
  return()
endif()

execute_process(
  COMMAND ${CMAKE_COMMAND} -E remove_directory "${repository_destination}"
  RESULT_VARIABLE error_code
  )
if(error_code)
  message(FATAL_ERROR "Failed to remove directory: '${repository_destination}'")
endif()

# Copy the repository to the destination
execute_process(
  COMMAND ${CMAKE_COMMAND} -E copy_directory
    "/home/nico/Desktop/Drone_Simulations/Fastdds"
    "${repository_destination}"
  RESULT_VARIABLE error_code
  )
if(error_code)
  message(FATAL_ERROR "Failed to copy repository to: '${repository_destination}'")
endif()

# Complete success, update the script-last-run stamp file:
execute_process(
  COMMAND ${CMAKE_COMMAND} -E copy
    "/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds-stamp/fastdds-gitinfo.txt"
    "/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds-stamp/fastdds-gitclone-lastrun.txt"
  RESULT_VARIABLE error_code
  )
if(error_code)
  message(FATAL_ERROR "Failed to copy script-last-run stamp file: '/home/nico/Desktop/Drone_Simulations/Micro-XRCE-DDS-Agent/build/fastdds/src/fastdds-stamp/fastdds-gitclone-lastrun.txt'")
endif()

```

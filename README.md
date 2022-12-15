# Flying a crazyflie drone through a mailbox slot
The drone must be capable of flying through a narrow slot constricted in x-z domain at some altitude h and land safely without losing control

## Installation
No separate python modules needed, the ae483 conda environment is sufficient.
The controller_ae483.c is meant to replace the one in ```ae483/crazyflie-firmware/src/modules/src/controller_ae483.c```
The flight.py code must be installed with the python file Final_Project_Data_Analysis in ```ae483/crazyflie-client/```

## File Explanation
The contents of the files are:
- move_data#.json files 
  - which are files that recorded successful runs and were used in analysis
- Final_Project_Data_Analysis.ipynb file
  - which is the anaysis software which compiles the .json files
  - runs a comparative analysis between the default, custom, and desired observer values for each variable and for the X-Y and X-Z planes 
  - compiling RMSE values at the end of each run
  - error plots for further comparison
- flight.py includes
  - modified flight commands for the drone to fly its straightline path
- controller_ae483.c contains 
  - software implementation of the height adjustment code which allows the project to work.

## Final_Project_Data_Analysis Structure
The code is structured in the following order
### Setup of the notebook
this contains importing modules, defining variables, matricies
### Flight Tests
#### Flight Test (repeat per slot)
- video
- data parsing
- comparing default and custom observers (plots)
- plot of position, desired position, and orientation (both from default and custom observer) over the entire flight test
- X-Y and X-Z plane plots
- RMSE values (table output form)
- Error Plots
  - Error between offline and default observer
### Flight Test Comparisons
- table of RMSE values from all 5 runs

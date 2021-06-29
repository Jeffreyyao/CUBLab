# CUBLab
## Starting the Lab

1. First make sure that the cameras and all four projectors are turned on and running.
2. Run the Motive program. Note that it should be run from the desktop shortcut to the calibrated arena, named "Motive best_calibration".
3. Run the localization server. This can be done by navigating to: D:Workspace/OptiTrackRESTServer/start_admin.bat. Open the start_admin file to begin running the server.

  - Check that the localization server is running properly. 
    - First place a rigid body in the arena, and go to the address: http://192.168.1.194:12345/OptiTrackRestServer. 
    - Make sure that the x,y coordinates and angle for any rigid body in the arena matches that which is showing at the server address.
    
4. Run Ventuz, the program that will connect our simulation to the projectors, by navigating to: D:Workspace/NDIRestServer/ventuz/NDIRestServerReceiver/Presentation/NDIRestServerReceiver.vpr. Run the program.
  - Make sure Ventuz is not already running before doing this step.
5. Start the simulation by navigating to: D:Workspace/pythonSimulator/simulate.py. Run the file simulate.py from terminal
6. Run the symbolic control server by navigating to: D:Workspace/pFaces-SymbolicControl/ex_gb_fp/deepracer/run_d_1_online.bat.
  - Check that the symbolc control server is running properly.
    - Open the file log.txt located in the same file path, using Notepad++.
    - Click on the eye icon on the upper tool bar in Notepad++. This will allow us to see the updates being made to the log file. 
7. Now we can run the robot.
We can access the DeepRacer robot by the following:
  ```
  $ ssh deepracer@192.168.1.70
  $ source /opt/aws/deepracer/setup.sh
  $ cd deepracer-utils
  $ python put_best_cal.py
  $ cd examples/sym_control
  $ python closedloop_online.py
  ```

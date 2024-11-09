# How to Use UR3e Trajectory Simulator

### Step 1: Generating .csv of Joint Angle trajectory

As a baseline, feel free to use the following link to generate a custom Lissajous curve [here](https://www.desmos.com/calculator/py01tjkbgb)

To generate a trajectory .csv based on a custom Lissajous curve, change the parameters on Lines 621-653 of the `custom_trajectory_generator.py` script.

To generate a trajectory .csv using your own custom curve, you can write additional helper functions to do so. See get_letter_trajectory() and uncomment lines 656-661

After setting up parameters, generate your csv by running the following within the `UR3e_ROS_Trajectory_Simulator/python_scripts` directory:
```
python3 custom_trajectory_generator.py
```

It may take up to a few minutes to generate the csv depending on how complex your curve is.

### Step 2: Simulating Trajectory in RVIZ
For Step 2, you will need to download and build the packages within the `ws3` workspace, which have been provided for you. 

You can build and source the workspace (if this is not working, open a new terminal and try again):
```bash
cd ./ws3 && colcon-build --symlink-install && source ./install/setup.bash
```
It is important that you have only sourced the `ws3` workspace. If you see an error message saying there are multiples packages with the same name, this is the issue.

You can run the following command to see if things are working:
```bash
ros2 launch msee22_description view_room.launch.py
```

Copy and paste your `custom_trajectory.csv` file into the `ws3/src/py_joint_pub/py_joint_pub/resource` folder. 
Finally, rebuild the package and source your workspace. You can visualize your robot's trajectory with
```
ros2 launch msee22_description move_robot.launch.py
```




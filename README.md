# How to Use UR3e Trajectory Simulator

### Step 1: Generating .csv of Joint Angles

As a baseline, feel free to use the following link to generate a custom Lissajous curve [here](https://www.desmos.com/calculator/py01tjkbgb)

To generate csv based on a custom Lissajous curve, change 

### Steps 1-3
For steps 1-3, you can use the MATLAB or Python starter code provided. First, make your own copy personal copy of the Lab 3 repo with the `Use This Template` button. Then, for MATLAB users, you will need to `git clone` this repository onto your personal computer via: If using Python, you have the option of cloning on your personal machine or on eceprog. If using eceprog, please run the `git clone` command from your home directory.


### Step 4
For Step 4, you will need to download and build the packages within the `ws3` workspace, which have been provided for you. In a new terminal on eceprog (or your own linux machine), in the home directory, clone your Lab 3 repo. It will download the entire repository, which is fine. All you really need is the `ws3` folder.

Then you can run the `setup-ros-workspace` tool from the home directory:
```bash
setup-ros-workspace ws3 humble
```
Then you can build and source the workspace (if this is not working, open a new terminal and try again):
```bash
rosd && cb && _ws3
```
It is important that you have only sourced the `ws3` workspace. If you see an error message saying there are multiples packages with the same name, this is the issue.

You can run the following command to see if things are working:
```bash
ros2 launch msee22_description view_room.launch.py
```

Then, in the `ws3/src/py_joint_pub/py_joint_pub/joint_publisher_csv.py` file, change line 18 to your filename. 
Also, copy and paste your `<username>.csv` file into the `ws3/src/py_joint_pub/py_joint_pub/resource` folder. 
A good way to get your CSV file into eceprog is to upload the file to github, and then run `git pull` on eceprog to download the changes back onto eceprog. Then, you can move the `.csv` file to the `resource` folder.
Finally, rebuild the package and source your workspace. You can visualize your robot's trajectory with
```
ros2 launch msee22_description move_robot.launch.py
```
Be sure to take a screenshot for your lab report.

### Bonus
You can upload a `.csv` file named `<username>_bonus.csv` which meets the requirements outlined in [Overleaf](https://www.overleaf.com/read/vrwwbkdxtxtz#e2ca05). Be sure this trajectory satisfies all requirements before uploading to Brightspace/Gradescope.

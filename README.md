<h1>Installing the Arduino Robot Arm Package on ROS (noetic) Step by Step</h1
<p>After setting up Ubuntu 20.04 ver on your Virtualbox, follow these steps to install ROS successfully:</p>

<h2>Step 1 - Creating a ROS Package</h2>
<p> To create Workspace run the following command consecutively:</p>

    mkdir -p ~/catkin_ws/src 
    cd ~/catkin_ws/ 
    catkin_make

<h2> Step 2 - Add the Arduino Robot Arm Package to "src" Folder</h2>
<p>In order to do this you have to run the commnds below in your terminal:</p>

    cd /catkin_ws/sre
    sudo apt install git
    git clone https://github.com/smart-methods/arduino robot arm

<h2>Step 3 - Install the Dependencies</h2>
<p>run this instruction inside your workspace:</p>

    rosdep install --from-paths src --ignore-src -r -y

<p>make sure you installed all these packages:</p>

    sudo apt-get install ros-noetic-moveit
    sudo apt-get install ros-noetic-joint-state-publisher ros-noetic-joint-state-publisher-gui
    sudo apt-get install ros-noetic-ros-controllers ros-noetic-ros-control
    
<h2>Step 4 - Configuring Arduino with ROS</h2>

First, Install Arduino IDE in Ubuntu from https://www.arduino.cc/en/software, then run the following command after unzipping the folder:

    sudo ./install.sh

Second, Launch the Arduino IDE

<h3>Third, Installing Binaries on the ROS workstation</h3>

You can install rosserial for Arduino by running:

    sudo apt-get install ros-noetic-rosserial-arduino
    sudo apt-get install ros-noetic-rosserial

<h3>Install ros_lib into the Arduino Environment</h3>

    cd <sketchbook>/libraries
    rm -rf ros_lib
    rosrun rosserial_arduino make_libraries.py .
    
<h4>Note:</h4> <sketchbook> is the directory where the Linux Arduino environment saves your sketches. Typically this is a directory called sketchbook or Arduino in your home directory. e.g cd ~/Arduino/libraries.

<h2>Finishing Up</h2>
After restarting your IDE, you should see ros_lib listed under examples:

![Finishing](https://github.com/DaleenSofyan/RobotArmPackgeInstallation/blob/main/Images/Finishing.png)

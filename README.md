# Remote Brainstorming - Omron Robotic Arm

Please download the software, [ACE from Omron](https://automation.omron.com/en/us/forms/ace-robot-software-download-request-form), to operate the robot. Please note the software is only compatible with Window System.

There are three wires coming out from the robotic arm:
  
- **Ethernaet Cable (with USB adapter)**: Use directly to program and run the robot controller with ACE software.
- **USB Cable (with Matt's name on it)**: Use to access the interior information from the controller, ex. resetting the timer.
- **USB Serial communication Cable (transparent one)**: Use to do serial communication with the processor.


Please refer to individual section detailed intructions or steps:
- [**Starting**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#starting-ace)
- [**Robot Control**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#robot-control)
- [**Drawing Area Setting and Calibration**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#drawing-area-calibration)
- [**Tasks Running**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#tasks-running)
- [**Processing**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#processing)


## Starting
1) Turn on the power of the robot with the switch on the power cord, make sure there is no loose plug. Wait for the controller to setup, the small monitor on the controller should display "I1" to "I6" while checking all 6 joints of the robot, if the robot is set up properly, the monitor will end up saying "OK". After seeing "OK", wait for a "click sound" from the robot to continue, it might take up to 1-2 mins, please be patient!

2) Connect the Ethernet cable and USB cable to your laptop. If you're using an adapter for the Ethernet cable, please make sure you install the driver for the adapter. 

3) Open the ACE software, you should see the image below. Go to the "Connect to Controller" page to check whether your laptop does detect the robot by clicking the refresh button, the robot option, Viper850, should appear on the list automatically with an IP address. If you are not able to see the option, you might need to turn off the FireWall on your laptop. Please close down ACE software, go to setting and turn off the FireWall option on your laptop and re-open ACE software again. When you see the robot option, please write down the IP address of the robot for later use.

(Insert Image)

4) Download the program file (awp.) we have for this project: [drawingProgram_V2.awp](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/drawingProgram_V2.awp).

5) Go back to ACE and go under the "Load Saved Workspace" page and open the program file (awp.) you just downloaded.

(Insert Image)

6) After launching the project, go to the menu on the left and double-click on "SmartController 50", you should be about to see the image as shown below. Check the IP address and see whether it matches the one you saw earlier from the robot list, if not, please change it.

(Insert Image)

7) Click on the connect button, it might take a while to load all the information and data. If it does not work, please try to re-open the software again with the steps above or try to re-start the robot. Double-check whether you turn off the FireWall on your laptop, it causes conflict with the robot.

(Insert Image)

8) After successfully connect to the robot, press the "Enable Power and Calibrate", shown in the image below. The software will ask you to press the "High Power" button on the emergency switch (physical one). Please look for the physical emergency switch, the high power button should be glowning while waiting for activation, press the button to activate.

(Insert Image)

9) If everything connects and activates successfully, you are ready for the next section!


## Robot Control
Before starting to run the program, you should know the orientation of the robot and the two ways we will be using here to move the robot.

### Orientation
- **x Direction**: Red arrow, toward the front of the robot. 
- **y Direction**: Green arrow, toward the left of the robot.
- **z Direction**: Blue arrow, toward the top of the robot.

(Insert Image)

### Control with EV+ Code


### Robot Control Panel


## Drawing Area Setting and Calibration
The way the program sets up the robot is to define a drawing area on a flate plane with three points: #righttop, #leftbottom, and #rightbottom. In this section, you will learn how to calibrate these three points and have the program remember them.

1) Open the robot control panel by clicking on the "Launch Robot Jog Control" button.

(Insert Image)

2) 


## Tasks Running




## Processing

[adeptRobotController_V2.pde](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/adeptRobotController_V2.pde)


```

```


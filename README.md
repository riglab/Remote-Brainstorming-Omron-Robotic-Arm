# Remote Brainstorming - Omron Robotic Arm

Please download the software, [ACE from Omron](https://automation.omron.com/en/us/forms/ace-robot-software-download-request-form), to operate the robot. Please note the software is only compatible with Window System.

There are three wires coming out from the robotic arm:
  
- **Ethernaet Cable (with USB adapter)**: Use directly to program and run the robot controller with ACE software.
- **USB Cable (with Matt's name on it)**: Use to access the interior information from the controller, ex. resetting the timer.
- **USB Serial communication Cable (transparent one)**: Use to do serial communication with the processor.


Please refer to individual section detailed intructions or steps:
- [**Starting**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#starting-ace)
- [**Drawing Area Setting and Calibration**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#drawing-area-calibration)
- [**Tasks Running**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#tasks-running)
- [**Processing**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#processing)


## Starting
1) Turn on the power of the robot with the switch on the power cord, make sure there is no loose plug. Wait for the controller to setup, the small monitor on the controller should display "I1" to "I6" while checking all 6 joints of the robot, if the robot is set up properly, the monitor will end up saying "OK". After seeing "OK", wait for a "click sound" from the robot to continue, it might take up to 1-2 mins, please be patient!

2) Connect the Ethernet cable and USB cable to your laptop. If you're using an adapter for the Ethernet cable, please make sure you install the driver for the adapter. 

3) Open the ACE software, you should see the image below. Go to the "Connect to Controller" page to check whether your laptop does detect the robot by clicking the refresh button, the robot option, Viper850, should appear on the list automatically with an IP address. If you are not able to see the option, you might need to turn off the FireWall on your laptop. Please close down ACE software, go to setting and turn off the FireWall option on your laptop and re-open ACE software again. When you see the robot option, please write down the IP address of the robot for later use.

4) Download the program file (awp.) we have for this project: [drawingProgram_V2.awp](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/drawingProgram_V2.awp).

5) Go back to ACE and go to the "Load Saved Workspace" page and open the program file (awp.) you just downloaded.

6) 

## Drawing Area setting and Calibration




## Tasks Running




## Processing

[adeptRobotController_V2.pde](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/adeptRobotController_V2.pde)


```

```


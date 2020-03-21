# Remote Brainstorming - Omron Robotic Arm

**Remember to hold the physical emergency stop button of the robot during the time you are controlling it, it can easily break things or hurt people. Press the red button immediately when anything goes wrong!!!**

Please download the software, [ACE from Omron](https://automation.omron.com/en/us/forms/ace-robot-software-download-request-form), to operate the robot. Please note the software is only compatible with Window System.


There are three wires coming out from the robotic arm:  
- **Ethernaet Cable (with USB adapter)**: Use directly to program and run the robot controller with ACE software.
- **USB Cable (with Matt's name on it)**: Use to access the interior information from the controller, ex. resetting the timer.
- **USB Serial communication Cable (transparent one)**: Use to do serial communication with the processor.


Please refer to individual section for detailed intructions or steps:
- [**Starting**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm#starting)
- [**Robot Control**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#robot-control)
- [**Drawing Area Setting and Calibration**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#drawing-area-setting-and-calibration)
- [**Tasks Running**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#tasks-running)
- [**Processing**](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/README.md#processing)


## Starting
1) Turn on the power of the robot with the switch on the power cord, make sure there is no loose plug. Wait for the controller to setup, the small monitor on the controller should display "I1" to "I6" while checking all 6 joints of the robot, if the robot is set up properly, the monitor will end up saying "OK". After seeing "OK", wait for a "click sound" from the robot to continue, it might take up to 1-2 mins, please be patient!

2) Connect the Ethernet cable and USB cable to your laptop. If you're using an adapter for the Ethernet cable, please make sure you install the driver for the adapter. 

3) Open the ACE software, you should see the image below. Go to the "Connect to Controller" page to check whether your laptop does detect the robot by clicking the refresh button, the robot option, Viper850, should appear on the list automatically with an IP address. If you are not able to see the option, you might need to turn off the FireWall on your laptop. Please close down ACE software, go to setting and turn off the FireWall option on your laptop and re-open ACE software again. When you see the robot option, please write down the IP address of the robot for later use.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Detecting%20Robot.PNG" width="500"/>
</p>

4) Download the program file (awp.) we have for this project: [drawingProgram_V2.awp](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/ACE%20Program/drawingProgram_V2.awp).

5) Go back to ACE and go under the "Load Saved Workspace" page and open the program file (awp.) you just downloaded.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Opening%20Project.PNG" width="500"/>
</p>

6) After launching the project, go to the menu on the left and double-click on "SmartController 50", you should be about to see the image as shown below. Check the IP address and see whether it matches the one you saw earlier from the robot list, if not, please change it.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Starting%20of%20the%20Project.PNG" width="500"/>
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_IP%20Address%20Checking.PNG" width="500"/>
</p>

7) Click on the connect button, it might take a while to load all the information and data. If it does not work, please try to re-open the software again with the steps above or try to re-start the robot. Double-check whether you turn off the FireWall on your laptop, it causes conflict with the robot.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Connect%20Button.jpg" width="500"/>
</p>

8) After successfully connect to the robot, press the "Enable Power and Calibrate", shown in the image below. The software will ask you to press the "High Power" button on the emergency switch (physical one). Please look for the physical emergency switch, the high power button should be glowning while waiting for activation, press the button to activate.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Enable%20Power.jpg" width="500"/>
</p>

9) If everything connects and activates successfully, you are ready for the next section!


## Robot Control

**Remember to hold the physical emergency stop button of the robot during the time you are controlling it, it can easily break things or hurt people. Press the red button immediately when anything goes wrong!!!**

Make sure you have turn on he high power mode so that the robot can actually move, step 8 from the last section.
Before starting to run the program, you should know the orientation of the robot and the two ways we will be using here to move the robot.

### Orientation
- **x Direction**: Red arrow, toward the front of the robot. 
- **y Direction**: Green arrow, toward the left of the robot.
- **z Direction**: Blue arrow, toward the top of the robot.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Robot%20Orientation.PNG" width="500"/>
</p>

### Control with eV+ Code
ACE software uses eV+ language to control the robot directly, we will list out a few common commands here. Go to ACE and open the "Montitor Window", your laptop need to be connected to the robot to be able to do so.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Monitor%20Window.jpg" width="500"/>
</p>

- **Setting Default Speed**
  
  The robot is actually really strong and can move really fast to hurt people. before starting to control it, it is recommended to set the default speed of the robot to lower value. 
  ```
  .do speed 10 always
  ```
  The value "10" here means the 10% of the full speed, as you can do 0-100 with the variable. The "always" here means dsetting the default, if you did not add it, the speed setting will only remain for the next command line.
  
- **Moving the Robot**
  
  The robot can be move under the world xyz coordinates with/without point-to-point straight line with the displacements you set.
  ```
  .do move shift (here by x,y,z)
  ```
  ```
  .do moves shift (here by x,y,z)
  ```
  -"move/moves shift" adding "s" means moving in straight line with the shift setting.
  
  -"here by" means seeing the original point as the staring point.
  
  -"x,y,z" will be the values of the displacements for three directions with the unit of mm.
  


### Robot Control Panel
Beside using direct commands to control the robot, you will be able to use the control panel from he ACE software.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Robot%20Control%20Panel.PNG" width="500"/>
</p>

- **Joint**
  This is a 6-DoF robotic arm, and you will be able to click on the individual joint and control the degree.

- **World Coordinates**
  With the orientation of the robot, you will be about to move it along the x,y,z directions.


## Drawing Area Setting and Calibration

**Remember to hold the physical emergency stop button of the robot during the time you are controlling it, it can easily break things or hurt people. Press the red button immediately when anything goes wrong!!!**

If you have set up the robot before without changing the position, you can skip this section.

The way the program sets up the robot is to define a drawing area on a flate plane with three points: #righttop, #leftbottom, and #rightbottom. The drawing area is usually setup somewhat parallel to the y-z plane of the robot. In this section, you will learn how to calibrate these three points and have the program remember them.

Please make sure you take down the cap of the marker before starting the process.

1) Open the robot control panel by clicking on the "Launch Robot Jog Control" button.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Robot%20Control%20Panel.PNG" width="500"/>
</p>

2) Three points you will need to define for the program: #righttop, #leftbottom, and #rightbottom corners of the drawing area. You can either use the control panel to move the robot around or move the robot with eV+ commands, which might be faster for longer displacment. 

3) While moving the robot around, please make sure the marker is not touching the drawing board, which is toward the x direction. Adjust the y and z directions to the position you want and slowly move in the x direction till the tip of the marker is pressing the drawing board. 

4) First point to do is usually the **#righttop** corner. After you find the point following the previous step, use the drop-down menu on the right top of the Robot Jog Control and chose "#righttop" and click the "Here" button, the program will remember the joint positions.
**Important: write down the y coordiante of this position, you will need it later when defining the #rightbottom.**

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Robot%20Control%20Panel.PNG" width="500"/>
</p>

5) Second point to do is the **#leftbottom** corner. It is the same as setting up the #righttop corner with the steps above. Please make sure the width and height of the drawing area does not exceed the limitation of the robotic arm. Use the drop-down menu on the right top of the Robot Jog Control and chose "#leftbottom" and click the "Here" button, the program will remember the joint positions.**Important: write down the z coordiante of this position, you will need it later when defining the #rightbottom.**

6) Finally, you will need to define the **#rightbottom** corner, it should be easier with the y coordiante from #righttop and z coordiante from #leftbottom. In this step, you are just going make sure the x coordiante of the #rightbottom corner to define the drawing plane. use the drop-down menu on the right top of the Robot Jog Control and chose "#rightbottom" and click the "Here" button, the program will remember the joint positions.

7) Write down the approxiate size of the drawing area you just set, the width and height, you would need them for the Processing program. 

8) After setting the three points, please move the robot away from the drawing board without touching it. If possible, move the robot to somewhere close to the center of the drawing area for later use. 

## Tasks Running

**Remember to hold the physical emergency stop button of the robot during the time you are controlling it, it can easily break things or hurt people. Press the red button immediately when anything goes wrong!!!**

1) Go back to the main screen of ACE and open the "Task Status Control", double-click on the "SmartController" to see the task status. For this controller, you will be able to run 4 different tasks, pre-program with eV+, simultaneously. The program we have here have two tasks:
- **bufferdraw**: the task that remembers #righttop, #leftbottom, and #rightbottom corners of the drawing area and calculates the movement.
- **readserial**: the task that communicate with Processing to get the drawing position, please refer to later section for Processing. 

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/ACE_Task%20Status%20Control.PNG" width="500"/>
</p>

For conventional setting, we will first setup "Task 1" with **readserial** and then setup "Task 0" with **bufferdraw**.

2) Right-click on "Task 1" and choose "start the task" and use the drop-down menu to find **readserial** task. Make sure the task start with a green flag indication.

3) Right-click on "Task 0" and choose "start the task" and use the drop-down menu to find **bufferdraw** task. Make sure the task start with a green flag indication. **Important: when the bufferdraw task starting to run, the robot will move in sequence from #leftbottom to center, center to #rightbottom, back to center, center to #righttop, and finally back to center. Please do not be scared by the sudden movement. During the same time, remember to hold the physical emergency stop button of the robot during the time you are controlling it, it can easily break things or hurt people. Press the red button immediately when anything goes wrong!!!**

4) Make sure that both of the tasks are running properly with green flags indication, if yes, you can proceed to the next section and start the Processing program. 

## Processing

We here use Processing as a medium to transfer the drawing/sketching to positions for the robotic arm. Processing is using serical communication through USB cale to send data to the robotic arm, please make sure you have connect both of the USB cables from the robot to your laptop before starting the program.

The code we have for Processing will setup window for drawing and you will need to set the size of the window to somewhat close to the proportion of the drawing area for the robot. The code will scale down the width and height to -1 to 1 and use serial communication to send date to the robot controller, the controller will then re-scale the width and height for actual drawing area.

1) Connect the **USB Serial communication Cable (transparent one)** to your laptop, you will need this to perform serial communication. 

2) Please download the Processing sketch here: [adeptRobotController_V2.pde](https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Processing%20Code/adeptRobotController_V2.pde).

3) Open the sketch with Processing.

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/Processing.PNG" width="500"/>
</p>


4) Find the following code in the sketch:
```
int screenSizeX = 1600;
int screenSizeY = 900;
```
Change the width and height to the sizes that fit the screen of your laptop, the unit is in pixel. Try to keep the proportion to somewhat close to the drawing area of the robot.


5) Find the following code in the sketch:
```
size (1600, 900);
```
Change the variables you have from the previous step.


6) Make sure you find the COM port for the robot **USB Serial communication Cable (transparent one)** before running the program. The code below is the line that define the serial communication port.
```
Serial roboPort = new Serial(this, Serial.list()[0], 9600);
```

7) After successfully lunching the program, you should be able to press the left-click of your mouse and draw on the launching window, the robot should do the exact same drawing you have!

<p align="center">
<img src="https://github.com/riglab/Remote-Brainstorming-Omron-Robotic-Arm/blob/master/Images/Processing_Drawing.PNG" width="500"/>
</p>


```


```
<p align="center">
<img src="" width="500"/>
</p>

# Index
  * [Motorola E4 Phones Disconnecting Momentarily (*Reported 10/2018*)](https://github.com/ftctechnh/ftc_app/wiki/Troubleshooting#motorola-e4-phones-disconnecting-momentarily-reported-102018)
  * [Manually Connecting to the Blocks Programming Mode Wi-Fi Network](https://github.com/ftctechnh/ftc_app/wiki/Troubleshooting#manually-connecting-to-the-blocks-programming-mode-wi-fi-network)
  * [Commonly Encountered Problems (Blocks)](https://github.com/ftctechnh/ftc_app/wiki/Troubleshooting#commonly-encountered-problems-blocks)

# Commonly Encountered Problems
### Motorola E4 Phones Disconnecting Momentarily (*Reported 10/2018*)
The Motorola E4 phone is approved for use in the _FIRST_ Tech Challenge.  In fall 2018, teams reported seemingly random disconnects between the Driver Station and Robot Controller devices when the E4 phones were used.

There is a thread on the FTC Technology Forum that describes the problem:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;https://ftcforum.usfirst.org/forum/ftc-technology/67146-moto-e4-phones-disconnecting

The posts suggest that the problem occurs when the Motorola E4 phone is acting as the Driver Station.  The phone seems to temporarily disconnect from the Robot Controller and then it quickly reconnects.  This can cause a problem when teams experience such a disconnect during a match.

A careful inspection of the Driver Station log file (which is located on the Driver Station Android phone with the filename "driverStationLog.txt") has log statements that look like the following:

```
11-21 12:18:08.541  5238  5714 V DriverStation: { -144  8.396} ui:uiWaitingForStartEvent 
11-21 12:19:19.212  5238  5717 V Robocol : { -144 19.068} issuing peerDisconnected(): lastRecvPacket=2.036 s 
11-21 12:19:19.214  5238  5717 E RobotCore: { -144 19.070} java.lang.Throwable: Peer disconnected 
11-21 12:19:19.219  5238  5717 E RobotCore: { -144 19.075}     at com.qualcomm.ftcdriverstation.FtcDriverStationActivity.peerDisconnected(FtcDriverStationActivity.java:1187) 
11-21 12:19:19.221  5238  5717 E RobotCore: { -144 19.076}     at org.firstinspires.ftc.robotcore.internal.network.SendOnceRunnable.run(SendOnceRunnable.java:132) 
11-21 12:19:19.222  5238  5717 E RobotCore: { -144 19.077}     at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:428) 
11-21 12:19:19.223  5238  5717 E RobotCore: { -144 19.079}     at java.util.concurrent.FutureTask.runAndReset(FutureTask.java:278) 
11-21 12:19:19.224  5238  5717 E RobotCore: { -144 19.080}     at java.util.concurrent.ScheduledThreadPoolExecutor$ScheduledFutureTask.run(ScheduledThreadPoolExecutor.java:273) 
11-21 12:19:19.225  5238  5717 E RobotCore: { -144 19.081}     at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1133) 
11-21 12:19:19.228  5238  5717 E RobotCore: { -144 19.084}     at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:607) 
11-21 12:19:19.229  5238  5717 E RobotCore: { -144 19.084}     at java.lang.Thread.run(Thread.java:761) 
11-21 12:19:19.229  5238  5717 V DriverStation: { -144 19.085} robot controller disconnected 
11-21 12:19:19.229  5238  5717 V DriverStation: { -144 19.085} Assuming client disconnected 
```

In the snippet of log statements above, you can see that at 12:18:08.541 an Op Mode calls the waitForStart() method to wait for a start command from the Driver Station.  Then you can see at 12:19:19.212 the Driver Station logs that it thinks it's disconnected from the Robot Controller since it hasn't communicated with the Robot Controller in over 2 seconds.

It appears that for some undetermined reason, when a Motorola E4 is acting as a Driver Station and the Robot Controller is running an op mode and is blocking in the waitForStart() method, the Driver Station appears to lose communication with the Robot Controller for over 2 seconds (even though it is supposed be sending heartbeat packets to the Robot Controller every tenth of a second or so).  When this happens the Robot Controller stops the op mode run for safety reasons.  In the Robot Controller log file (which has the name "robotControllerLog.txt" on the Android device acting as the Robot Controller) you can see statements like the following:

```
11-22 01:19:19.064  5935  6013 V Robocol : issuing peerDisconnected(): lastRecvPacket=2.035 s
11-22 01:19:19.066  5935  6013 V UpdateUI: Network: active, disconnected
11-22 01:19:19.068  5935  6013 I RobotCore: ******************** STOP - OPMODE /storage/emulated/0/FIRST/matchlogs/Match-0-Concept:_Vuforia_Rover_Nav.txt ********************
11-22 01:19:19.073  5935  6163 I RobotCore: saving match logcat to /storage/emulated/0/FIRST/matchlogs/Match-0-Concept:_Vuforia_Rover_Nav.txt
11-22 01:19:19.073  5935  6163 I RobotCore: logging command line: exec logcat -d -T '11-22 1:18:8.000' -f /storage/emulated/0/FIRST/matchlogs/Match-0-Concept:_Vuforia_Rover_Nav.txt -n4 -v threadtime UsbRequestJNI:S UsbRequest:S art:W ThreadPool:W System:W ExtendedExtractor:W OMXClient:W MediaPlayer:W dalvikvm:W  *:V
11-22 01:19:19.073  5935  6013 I RobotCore: Lost connection while running op mode: Concept: Vuforia Rover Nav
11-22 01:19:19.093  6164  6164 W sh      : type=1400 audit(0.0:223): avc: denied { read } for uid=10135 name="/" dev="rootfs" ino=2 scontext=u:r:untrusted_app:s0:c512,c768 tcontext=u:object_r:rootfs:s0 tclass=dir permissive=0
11-22 01:19:19.124  5935  6002 V SoundInfo: construct(0x0e74e3bd)
11-22 01:19:19.168  5935  6163 I RobotCore: Done running exec logcat -d -T '11-22 1:18:8.000' -f /storage/emulated/0/FIRST/matchlogs/Match-0-Concept:_Vuforia_Rover_Nav.txt -n4 -v threadtime UsbRequestJNI:S UsbRequest:S art:W ThreadPool:W System:W ExtendedExtractor:W OMXClient:W MediaPlayer:W dalvikvm:W  *:V
11-22 01:19:19.169  5935  6163 I RobotCore: exiting match logcat for /storage/emulated/0/FIRST/matchlogs/Match-0-Concept:_Vuforia_Rover_Nav.txt
```

As a workaround to this problem on the Motorola E4 phones, some members of the _FIRST_ community discovered that if the Robot Controller sends telemetry messages to the Driver Station while the Robot Controller is waiting for a start command from the Driver Station, the phones will not disconnect.

#### Workaround for Blocks Users

If you are a Blocks programmer, instead of using the "waitForStart" block (which is disabled in the screenshot below), you should use the "opModeIsActive" and "isStopRequested" blocks to create a loop that sends telemetry data to the Driver Station while waiting for the start command.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/troubleshooting/blocksE4Fix.png" width="900"><p>

If you use this alternate way to wait for a start command, then the Robot Controller will constantly send telemetry messages to the Driver Station while it is waiting.  This seems to prevent the disconnects that are reported with the E4 phones. 

#### Workaround for a Java Linear Op Mode

If you are a Java programmer and you are using a LinearOpMode, instead of using the waitForStart() method (which is commented out in the code snippet below), you should use the opModeIsActive() and isStopRequested() methods to create a loop that sends telemetry data to the Driver Station while waiting for the start command.

```
        // Do not use waitForStart() if you have Motorola E4 phones.
        //waitForStart();
        while (!opModeIsActive() && !isStopRequested()) {
            telemetry.addData("status", "waiting for start command...");
            telemetry.update();
        }
```

If you use this alternate way to wait for a start command, then the Robot Controller will constantly send telemetry messages to the Driver Station while it is waiting.  This seems to prevent the disconnects that are reported with the E4 phones. 

#### Workaround for a Java Iterative Op Mode

If you are a Java programmer and are using an iterative OpMode, you should define your own init_loop() method and put a telemetry statement to send data to the Driver Station while waiting for the start command.

```
    @Override
    public void init_loop() {
        // If you are using Motorola E4 phones, 
        // you should send telemetry data while waiting for start.
        telemetry.addData("status", "loop test... waiting for start");
    }
```

If you add this init_loop() method, then the Robot Controller will constantly send telemetry messages to the Driver Station while it is waiting.  This seems to prevent the disconnects that are reported with the E4 phones. 

### Manually Connecting to the Blocks Programming Mode Wi-Fi Network

The section of this wiki with the title [Connecting Your Laptop to the FTC Blocks Programming Mode Server](https://github.com/ftctechnh/ftc_app/wiki/Writing-an-Op-Mode-with-FTC-Blocks#connecting-your-laptop-to-the-ftc-blocks-programming-mode-server) describes how to search for the blocks programming mode Wi-Fi network from a list of available networks and then connect to it with a Windows laptop.  For some Windows devices, the laptop might not display your blocks programming mode Wi-Fi network in its list of available networks.  This problem can occur with some Windows 10 machines (and possibly with some Windows 8 machines), especially if the computer does not have current system updates and service packs. 

If you are having problems seeing your FTC Blocks Programming Wi-Fi network in your list of available networks, make sure that your Driver Station is paired and connected to your Robot Controller (see the section called [Pairing the Driver Station to the Robot Controller](https://github.com/ftctechnh/ftc_app/wiki/Configuring-Your-Android-Devices#pairing-the-driver-station-to-the-robot-controller) of this document).  Also, make sure that your Robot Controller is in Programming Mode.  Also, make sure that your Windows 10 device has its most current updates installed from Microsoft.

If you have verified that the Driver Station is paired and connected to the Robot Controller and that the Robot Controller is in Programming Mode, and if you have verified that your Windows 10 updates are current, then you might have to manually connect your Windows 10 computer to the blocks programming mode Wi-Fi network.

You can manually connect to this network as if the network were a hidden network (i.e., a network that does not broadcast its presence to other Wi-Fi devices).  

Note that it will take an estimated 15 minutes to complete this task.

| Manually Connecting to the Programming Mode Wi-Fi Network |
| ---- |
| 1. In the lower right hand corner of the Windows 10 desktop, click on the network icon in the system tray to display a list of available Wi-Fi networks.<br/><br/><p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ManuallyConnectingStep1.jpg" width="175"></p>If you still do not see your Blocks Programming Mode Wi-Fi network listed, then scroll to the bottom of the list and look for the item called “Hidden Network”. |
| 2. Click on the “Hidden Network” listing to start the connection process.  The listing should display a “Connect” button.<br/><br/><p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ManuallyConnectingStep2.jpg" width="175"></p>Make sure the option “Connect automatically” is checked and then click on the “Connect” button to continue with the process. |
| 3. The computer should prompt you for the name or SSID of your blocks programming mode Wi-Fi network. You should type in the network name that is displayed in the Programming Mode window of the Android device.<br/><br/><p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ManuallyConnectingStep3.jpg" width="300"></p>Note that the SSID or network name is case sensitive.  Make sure the capitalization of the name that you enter matches the capitalization of the name displayed in the Programming Mode Window. |
| 4. The computer should then prompt you for the passphrase to access this Wi-Fi network.  You should type in the network passphrase that is displayed in the Programming Mode window of the Android device.<br/><br/><p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ManuallyConnectingStep4.jpg" width="225"></p>Note that the passphrase is case sensitive.  Make sure that your spelling and capitalization matches the original spelling and capitalization shown on the Programming Mode screen. |
| 5. Your computer will prompt you on whether you want to make your PC discoverable by other devices on this network.  Click “Yes” to continue.<br/><br/><p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ManuallyConnectingStep5.jpg" width="225"></p> |
| 6. The computer will attempt to connect to your network. Note that it could take several minutes before it connects.<br/><br/><p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ManuallyConnectingStep6.jpg" width="225"></p> |
| 7. If you could successfully connect to the network, it will eventually appear in the list of networks on your computer.  <br/><br/><p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ManuallyConnectingStep7.jpg" width="225"></p>Note that when your computer is connected to the blocks programming server on your Robot Controller phone, _it will not have access to the Internet._ |

### Commonly Encountered Problems (Blocks)
#### Cannot See the Blocks Programming Mode Wireless Network
If you are trying to connect to the blocks programming mode wireless network so that you can create/edit an op mode for your Robot Controller, but you cannot see this wireless network listed as an available network for your laptop to connect to, verify the following items:
1. Make sure the Driver Station is successfully paired to the Robot Controller (see section for details).  Often the Robot Controller’s Wi-Fi Direct network will time out if it is not connected to the Driver Station.
2. Make sure the Robot Controller has been switched successfully to programming mode (see section 0).
3. Power cycle (turn off and then turn back on) your Robot Controller phone and then relaunch the FTC Robot Controller app.  Reconnect the Driver Station to the Robot Controller, and then turn off the wireless adapter on your laptop for a few seconds, and then turn it back on (to force a rescan of the available Wi-Fi networks).

#### “Save project failed. Error code 0.”
If you attempt to save the op mode that you are currently editing, but you receive an error message indicating that the “Save project failed. Error code 0.” you might not be connected to the blocks programming mode sever:
1. Make sure the Robot Controller is in programming mode.
2. Make sure that your laptop is connected to the blocks programming mode Wi-Fi network.
3. If you have verified the first two items, press the “Save Op Mode” button again to re-attempt the save operation.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/SaveProjectFailed.jpg" width="500"><p>

#### Op Mode Blocks Are Missing…
If you have opened an existing op mode to edit it in your Javascript-enabled browser, but the programming blocks are missing, check the following:
1. Did you remember to save the op mode the last time you edited and then exited the op mode?  If you did not save the op mode after the last editing session, you might have lost some of your changes.
2. Are the blocks collapsed and/or in an area of the design “canvas” (or design pane) that is outside your current browser window?  If so, you can use the expand and cleanup functions of the blocks programming tool to expand all the blocks on your screen and to organize them in an easy-to-view (and easy-to-find) manner.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ExpandBlocks.jpg" width="450"><br/><sub>Right mouse click on “canvas” and select Expand Blocks to expand all of the blocks in your op mode. <p>

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/CleanUpBlocks.jpg" width="450"><br/><sub>Right mouse click on the canvas/design pane and select Clean up Blocks to organize all your blocks.<p>

3. Are your programming blocks missing and you only see a solitary gray rectangular block on your screen?  If this is the case, then you should check to see if the active configuration file for the Robot Controller is the same configuration file that you originally used to create the op mode.  There is a bug in early versions of the blocks programming software that prevents the blocks server from properly rendering the programming blocks if the active configuration of the Robot Controller does not match the original configuration file used to create the op mode.  More specifically, if some of the hardware devices (such as the DC motors or servos) from the original file are missing from the current configuration file, the blocks mode server will not properly display the programming blocks in the design pane.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/BlocksMissingGray.jpg" width="450"><p>

#### Driver Station is Unresponsive or Slow
If you are ready to run an op mode, but the Driver Station is unresponsive and you cannot initialize or start your selected op mode, check the following items:
1. Verify that the Driver Station is properly paired to the Robot Controller.
2. Make sure that the Robot Controller is not in Programming Mode.
3. Check the ping times on the Driver Station main screen.  The ping time is the average time it takes for the Driver Station to send a message to the Robot Controller and for the Robot Controller to acknowledged that it received the message.  If the ping time is low (< 20 msec) the wireless connection between the Driver Station and Robot Controller is good.  If the ping time is consistently high (> 50 msec) there could be some wireless interference in your venue that is causing the problems between the Driver Station and the Robot Controller.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/PingTime.jpg" width="175"><p>

#### "Warning: problem communicating..."

If you are trying to run an op mode and you notice error messages like the ones displayed below, it could be that your wired connection between the phone and the electronic modules is bad.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ProblemCommunicating.jpg" width="400"><p>

If you notice this error message, here are some things you can try:
1. Verify that the USB cable connecting the phone to the Expansion Hub is secure and well connected.
2. Verify that the 12V power cables connecting the battery to the switch and the Expansion Hub are properly secured and connected.  Also, verify that the power switch is in the on position.
3. Try to do a “Restart Robot” from the pop up menu (touch the three vertical dots in the upper right hand screen of the Robot Controller or Driver Station apps).
4. If that does not work, disconnect the USB cable from the phone, then shut down the main power switch on the Expansion Hub.   Wait for 5 seconds, then power the device back on and reconnect the USB cable to the phone.

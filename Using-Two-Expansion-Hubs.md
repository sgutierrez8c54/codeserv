### Introduction 
A single REV Robotics Expansion Hub has a limited amount of input/output (I/O) ports available. In some instances, you might want to use more devices than there are ports available.  For these instances you might need to connect a second Expansion Hub to your first Hub to add more I/O ports. 

This document describes how to connect and configure two Expansion Hubs for use in the FIRST Tech Challenge.  Note that the FIRST Tech Challenge Game Manual Part 1 (rule \<RE07\>, part f) limits the maximum number of Expansion Hubs on a single robot to two.  

### Equipment Needed 
To follow along with the instructional steps in this document, you will need the following items:

| Required Item(s) | Image |
| ----------- | :---: |
| Two (2) _FIRST_-approved Android smartphones.<br/><br/>One should have the FTC Robot Controller app installed<br/>and the other should have the FTC Driver Station app installed.<br/><br/>For a list of _FIRST_-approved Android smartphones, refer to the <br/>current FTC Game Manual Part 1, rule \<RE06\>. | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/twoAndroidPhones.jpg" alt="2 Android Phones" width="150"> |
| USB Type A male to type mini-B male cable. | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/USBTypeACable.jpg"  width="100"> |
| Micro USB OTG adapter. | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/OTGAdapter.jpg"  width="100"> |
| REV Robotics Switch, Cable, & Bracket (REV-31-1387). | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/REVSwitch.jpg"  width="100"> |
| REV Robotics Tamiya to XT30 Adapter Cable (REV-31-1382). | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/TamiyaAdapter.jpg"  width="100"> |
| _FIRST_-approved 12V Battery (such as Tetrix W39057).<br/><br/>For a list of _FIRST_-approved 12V batteries, refer to the current<br/>FTC Game Manual Part 1, rule \<RE03\>. | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Battery.jpg"  width="100"> |
| Two(2) REV Robotics Expansion Hubs (REV-31-1153). | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ExpansionHub.jpg"  width="100"> <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/ExpansionHub.jpg"  width="100"> |
| REV Robotics (or equivalent) 3-Pin JST PH Cable<br/>(REV-35-1414, 3 pack shown but only one needed). | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/3PinJSTPH.jpg"  width="150"> |
| REV Robotics XT30 Extension Cable (REV-31-1394). | <img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/xt30Extension.jpg"  width="150"> |

### Checking the Address of an Expansion Hub 
Before you connect your two Expansion Hubs together, you should first check the serial addresses associated with each of the Hubs.   

Each Expansion Hub has a serial address assigned to it at the factory.   By default, this serial address is the same for all Hubs.  If you want to connect two Expansion Hubs together, then you will have to change the address of one of your Hubs. 

You can determine the address of an Expansion Hub by connecting it to a 12V battery and to your Robot Controller.  Create and save a temporary configuration file for your Expansion Hub.  You do not need to have any motors, servos, or sensors defined in your configuration file, but the attached Expansion Hub must be included in the file.  Note that after we change the address of the Expansion Hub we will eventually delete this temporary configuration file. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/CheckAddressHardware.jpg" width="500"> </p>

After you have saved the configuration file and returned to the main screen of the Robot Controller app, the Expansion Hub's LED should enter a state where it turns green for a few moments (indicating that it's successfully connected to a Robot Controller) and then it will blink blue for a number of times equivalent to the device's address. 

For example, if your Expansion Hub has an address of 2, and it is successfully connected to a Robot Controller and powered by a12V battery, the blink sequence that will repeat for the LED is as follows,
 
<p align="center">GREEN (long) --> BLUE (short) --> BLUE (short)</p>
 
This sequence will repeat over and over again. 

Use this process to check the serial addresses for each of your Expansion Hubs.  Note that the factory default address is 2. 

### Changing the Address of an Expansion Hub 
You can use the Advanced Settings menu of the FTC apps to change the address of an Expansion Hub.  Note that it is recommended that when you change the address of an Expansion Hub, you only connect one Expansion Hub to the Robot Controller during the change address process.

With your Expansion Hub connected to the 12V battery and to the Robot Controller, launch the Settings menu from Robot Controller app (note you can also do this from the Driver Station app, if the Driver Station is paired to the Robot Controller).
   
Select the Advanced Settings item to display the Advanced Settings menu. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/AdvancedSettings.jpg" width="175"> </p>

Then select the Expansion Hub Address Change item to display the Expansion Hub address screen. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/ExpansionHubAddressChange.jpg" width="175"> </p>

The USB serial number of the Expansion Hub and its currently assigned address should be displayed.  By default, the factory assigned address is 2.  

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/DefaultAddress.jpg" width="175"> </p>

Use the dropdown list control on the right hand side to change the address to a non-conflicting value. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/NewAddress.jpg" width="175"> </p>

Push the "Done" button to change the address.    You should see a message indicating that the Expansion Hub's address has been changed. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/AddressChangeComplete.jpg" width="175"> </p>

### Warning: Expansion Hub "Expansion Hub2" is missing 
After the address has been successfully changed, if you return back to the main screen of your Robot Controller app (which will restart the robot), you should see an error message indicating that the Robot Controller can no longer find the Expansion Hub that you configured earlier.  This is because the configuration file was created with the original address of the Expansion Hub. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/ExpansionHub2Missing.jpg" width="175"> </p>
  
You can delete the temporary configuration that was made with the old address, and then create a new configuration file for the Expansion Hub's new address.  Save the new configuration file and return to the main Robot Controller screen.  The Expansion Hub should blink the new address value after the robot restart. 

### Connecting the Two Expansion Hubs 
After you have changed the address of one of the Hubs, you can use the 3-pin JST PH cable and the XT30 cable to daisy chain the two Hubs together.  Before you do this, disconnect the 12V battery and power switch from the first Expansion Hub.

Use the XT30 extension cable to connect an XT30 power port on one of the Expansion Hubs to an XT30 power port on the other Hub.

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/XT30ExtensionConnected.jpg" width="300"> </p>
 
The Expansion Hubs use the RS-485 serial bus standard to communicate between devices.  You can use the 3-pin JST PH cable to connect one of the ports labeled "RS485" on one Expansion Hub to one of the ports labeled "RS485" on the other Expansion Hub.  

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/RS485Connected.jpg" width="300"> </p>

Note that it is not important which "RS485" port that you select on an Expansion Hub.  Either port should work. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/RS485Port.jpg" width="300"> </p>

Once you have the two devices daisy chained together (12V power and RS-485 signal) you can reconnect the battery and power switch, and then connect the Robot Controller and power on the devices. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/DualConnected.jpg" width="500"> </p>

### Configuring Your Expansion Hubs 
If you were able to successfully daisy chain your two Expansion Hubs, then you should be able to create a new configuration file that includes both devices.

Connect the Robot Controller and select the Configure Robot option from the Settings menu.  Press the New button to create a new configuration file.  When you first scan for hardware, your Robot Controller should detect the Expansion Hub that is immediately connected to the Robot Controller via the OTG adapter and USB cable.  The Robot Controller will automatically label this device as an Expansion Hub "Portal".  The Robot Controller will talk through this portal to the individual Expansion Hubs. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/ExpansionHubPortal.jpg" width="175"> </p>

If you click on the Portal item in the configuration screen, you should see two Expansion Hubs listed, each with their respective addresses as part of their default device name. 

<p align="center"><img src="https://github.com/FIRST-Tech-Challenge/WikiSupport/blob/master/ftc_app/images/Advanced/TwoExpansionHubs/TwoHubsConfigured.jpg" width="175"> </p>
 
You can save this configuration file and return to the main screen of the Robot Controller.  After the robot has been restarted, each hub's LED should be blinking in the manner that indicates its individual address. 
  
Congratulations, you are now ready to use your dual Expansion Hubs!  You can configure and operate these Hubs as you would an individual Hub. 

*Quick links :*
[Home](/README.md) - [**Part 1**](../part1/README.md) - [Part 2](../part2/README.md) - [Part 3](../part3/README.md) - [Sensors](/en/sensors/README.md)
***
**Part 1** - [Setup](PREREQ.md) - [**First App**](FIRSTAPP.md) - [WIFI](WIFI.md) - [LED](LED.md) - [DHT](DHT.md) - [Cloud](IOTCLOUD.md)
***

# Your first ESP32-CAM application

## Lab Objectives

This Lab will show you how to use the Arduino IDE with the ESP32-CAM plugin to create a new application for the ESP32-CAM board.  You will learn how:

- Ensure you have the correct settings in the IDE
- How to compile source code into a binary
- How to upload a binary onto the board
- You should also take time to understand the flow of an Arduino application, and the purpose of the **setup()** and **loop()** functions.

### Step 1 - Setting up the Arduino environment for the ESP32-CAM

Let's start with a simple application to display information about the flash memory.  Start by setting up your Arduino IDE to the correct settings for the board.  Using the *Tools* menu, ensure the following settings are set:

- Board : **AI Thinker ESP32-CAM**
- Port : *Connect the ESP32-CAM to your laptop using FTDI USB to TTL Serial Converter Adapter Module and then select your port, depending on OS*

### Step 2 - Loading an example sketch

Then choose *File* -> *Examples* -> *ESP32* -> *ChipID* -> *GetChipID* from the menu to open a new window with the sample sketch preloaded (you can close the previous window as it is not needed).  This sketch will print out the ChipID which is the MAC address in reverse byte order.  

Example:

- ESP32 Chip ID = A0CC4DBF713C
- MAC Address = 3C:71:BF:4D:CC:A0

### Step 3 - Compiling the sketch

![Verify command](../images/verify.png)

You can now compile the sketch for the ESP32-CAM by selecting the **Verify** button on the command bar (tick icon) or using the *sketch* -> *Verify/Compile* menu option.  You will see there are keyboard short cuts for various commands, shown next to the menu option which you may want to learn and use.

### Step 4 - Uploading the sketch

![Upload command](../images/upload.png)

Once the compile has finished you can upload the new application to your ESP32-CAM using the **upload** button on the command bar (arrow to right icon) or using the *Sketch* -> *Upload* menu option.

*Note*: *you don't need to compile then upload.  Just using upload will compile the application if necessary then upload it to the ESP32-CAM*

If you try to save the sketch you will be prompted to enter a name/location for the sketch.  This is because the example sketches are read-only, if you want to modify them and save the modification you need to save it to a new location.

This example sketch prints out information about the flash memory on board the ESP32-CAM.  To see the output you need to open up the Serial Monitor.

![Serial Monitor](../images/SerialMonitor.png)

Ensure the baud rate at the bottom of the monitor window matches the baud rate in the setup function of the sketch `Serial.begin(115200);`.

### Step 5 - Understand the example sketch

The Arduino IDE and runtime take care of the work needed to setup the runtime for an application and provides 2 entry points.  A **setup()** function, which is called at the start of the application, or when the device comes out of a deep sleep.  The other entry point is the **loop()** function which is repeatedly called so long as the device is running.

There is no operating system running under the Arduino application, the code you enter in setup and loop is all that is running on the ESP32-CAM CPU.

This example sketch initialises the Serial connection in the **setup()** function then retrieves and prints information about the flash memory to the Serial console in the **loop()** function.  At the end of the **loop()** function there is a delay for 5 seconds (5000 milliseconds).  After the delay the **loop()** function ends, but is immediately called again.

***
*Quick links :*  
**Part 1** - [Setup](PREREQ.md) - [**First App**](FIRSTAPP.md) - [WIFI](WIFI.md) - [LED](LED.md) - [DHT](DHT.md) - [Cloud](IOTCLOUD.md)
***
[Home](/README.md) - [**Part 1**](../part1/README.md) - [Part 2](../part2/README.md) - [Part 3](../part3/README.md) - [Sensors](/en/sensors/README.md)

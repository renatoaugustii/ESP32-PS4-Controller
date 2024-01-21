# Connecting a PS4 Controller to ESP-32

#### Welcome to this repository dedicated to simplifying the process of connecting a PlayStation 4 (PS4) controller to an ESP-32 microcontroller. Whether you're working on a robotics project, IoT application, or simply exploring the possibilities of integrating a PS4 controller with an ESP-32, this repository provides the necessary codes and software resources.


## Hardware Requirements:
- ESP-32 Microcontroller
- PlayStation 4 (PS4) Controller
- Usb cable for PS4 Controller

## Software Requirements:
## Software Requirements:

- **IDE Arduino:** Version 2.2.2 or higher.
- **SixaxisPairToolSetup:** Version 0.3.1 or higher.
- **PS4Controller Library:**  Version 2.1 or higher.
-  **ESP32 Board Package:** 2.0.11 or higher by Espressif Systems Version .

These software components are essential for the successful setup and communication between the ESP-32 and the PS4 controller. Make sure to have the specified versions or newer to ensure compatibility and access to necessary features.

Feel free to reach out if you have any questions or encounter issues during the software setup process.


## Preparation:
- Confirm that your ESP-32 is operational and communicating correctly with the Arduino IDE. We won't go into detail on this process, as it's assumed to be a prerequisite.

## Board Manager:
- Add the following URL to the Additional Boards Manager in the Arduino IDE: `https://dl.espressif.com/dl/package_esp32_index.json`

## Library Installation:
- Install the ESP-32 library within the Arduino IDE. This tutorial is based on IDE version 2.2.2, and while newer versions should work, if any issues arise, please open an issue for an updated procedure.

## PS4 Controller Library:
- Install the PS4 controller library directly from the Arduino IDE:
  - Navigate to `Sketch > Include Library > Manage Libraries`.
  - Search for "PS4Controller" by Juan Pablo Marquez.

## MAC Address Discovery:
- Obtain the MAC address of your PS4 controller. To find the MAC address, use the `SixaxisPairToolSetup-0.3-1` software. Pay attention to the version number; in this tutorial, version 0.3.1 is recommended. Download all files from this repository, including the `SixaxisPairToolSetup-0.3-1` software, and install it.

# Sixaxis Pair Tool Setup

When you open the Sixaxis Pair Tool Setup software, the window below will be displayed.

![Sixaxis Pair Tool Setup Window](https://github.com/renatoaugustii/ESP32-PS4-Controller/blob/main/img/SixaxisPairTools%20Photo.png)

Now, you should connect the PS4 controller to your computer using the USB cable while the software is installed. Once connected, the MAC address will be identified. There is no need to alter this address; simply make a note of it in a secure location as we will use it in our ESP-32 code.

![Sixaxis Pair Tool Setup Window](https://github.com/renatoaugustii/ESP32-PS4-Controller/blob/main/img/SixaxisPairTools%20Photo%20MacAddress.png)

To proceed, follow these steps:

1. Connect the PS4 controller to your computer using the USB cable while the Sixaxis Pair Tool Setup software is installed.
2. Once connected, the MAC address will be identified by the software.
3. Make a note of the MAC address in a secure location, as we will use it in the upcoming ESP-32 code.

Keep in mind that the PS4 controller doesn't need to be connected during this initial setup; its MAC address is essential for configuring communication in the following steps.

# Test Code

Let's proceed with testing the connection using an example from the PS4Controller library. Follow these steps:

1. Open the PS4ReceivedData example code: `File > Examples > PS4Controller > PS4ReceivedData`.
2. A new instance of the code will be opened.

Upon opening the code, ensure to modify the MAC address within the code. Edit the following function:

```cpp
PS4.begin("00:e0:4c:bd:44:03");
```

Replace the MAC address inside the double quotes with the one you noted earlier. Once this modification is done, we are ready to upload the code to the ESP-32.

# Upload to ESP-32:

Ensure that the COM port is correctly configured for your ESP-32.
Set the Serial Monitor to a baud rate of 115200.
Upload the code to your ESP-32.
Controller Connection:

After the upload is complete, turn on the PS4 controller.
Check if the controller successfully connects to the ESP-32.

# Important Note:
Avoid Other Connections: Ensure that no other devices attempt to connect to the controller during this process, as it may cause connection issues with the ESP-32.
Feel free to troubleshoot any issues, and if you encounter difficulties during this process, reach out for assistance.


# Conclusion
This Markdown code provides clear instructions for users to modify the MAC address in the example code and upload it to the ESP-32 for testing the connection with the PS4 controller. Adjust the instructions as needed based on your preferences and additional details.


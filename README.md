# CitraVirtualControler
A basic virtual controller for the Citra Emulator (or other emulators) built using VJoy and Python. An example can be seen here: https://www.youtube.com/watch?v=VaLlZBzErxw

# Features
Simulates a virtual controller compatible with the Citra Emulator.
Can be adapted to work with other emulators.
Prerequisites
Before starting, make sure your system meets the following requirements:

# VJoy Installation
VJoy is a tool that allows your computer to detect virtual controllers. You can download it from https://sourceforge.net/projects/vjoystick/.

# Python Installation

This project requires Python to run. If Python is not installed on your computer, you can download it from https://www.python.org.
During installation, ensure you check the box to add Python to your system's PATH.

# Basic Command Line Knowledge

You’ll need to use the command line to navigate to folders and run commands. You can always open a command line by searching for 'cmd' on your device. common commands:

cd -> set a directory. for instance cd D:\Emulators\Citra\nightly will navigate to the 'nightly' folder.
cd.. will move one folder back. e.g. D:\Emulators\Citra\nightly and then cd.. gives D:\Emulators\Citra\

# Installation Guide
Follow these steps to set up the virtual controller:

1. Click on the green "Code" button at the top of this repository.
Select "Download ZIP."
Extract the contents of the ZIP file to a folder of your choice.
Install Required Python Packages

2. Open a terminal window:
On Windows: Right-click inside the folder containing the extracted files and select Open in Terminal. Alternatively, you can open the Command Prompt and navigate to the folder using the cd command.
Run the following command to install dependencies:
`pip install -r requirements.txt`

# Start the Virtual Controller

In the terminal, type the following command to start the virtual controller:
`python -m VirtualControler.py`. Note that this needs to be done in the same folder as during the installation.

# Troubleshooting
Depending on your system, VJoy may detect a device that is not device 1. In that case, you will need to alter the code slightly to make sure it uses the correct virtual controller for your system.
You can do this by:

1. Open the VJoy device list and check which devices are not greyed out. 
2. Open Monitor VJoy and check what happens when you run the app and press a button on it. For instance, lets assume Monitor Vjoy defaults to device #1, but pressing a button does nothing. Then you can select one of the other active devices from its dropdown menu (e.g device #9) and check whether that does trigger a response.
3. In the case above, we would then have to open the VirtualControler.py file and chance line 7 from `joy = pyvjoy.VJoyDevice(1)` to `joy = pyvjoy.VJoyDevice(9)`

# Citra setup
In order to use this controler with Citra, you will need to set up a new controler by going to 'emulation->configure-> controls'. Then set up all the buttons like you would with any other controler (Note: to register a button in citra you need to press it and let go, so for instance, for the a button, you need to check AND uncheck the button before citra configures it).

# Missing features
The virtual contoler does not provide exact Gyro input. However, it can be paired with regular mouse control to use gyro strategies (e.g. you can set the control stick to tilt down, and then use your mouse to do a gyro right input).


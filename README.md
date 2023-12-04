# autonomous-bittle
This repository holds the code and configuration for the autonomous swarm robotics project in the CMU-MAIL lab

# Set up raspberry pi
1. Flash image using raspberry pi imager:
   - raspberry pi OS (Legacy) Lite Bullseye
2. On first Power up:
   - Select Keyboard layout
   - set pi as username, select password
   - Log in
3. Set up wifi:
   - sudo raspi-config
   - Localisation Options
   - Set Timezone and WLAN Country
   - go to Advanced Options, set network config to use NetworkManager
   - go to system settings, enter wifi ssid and password
5. Set auto login:
   - 1. S5 Boot / Auto Login
6. Set up interface options
   - 3 Interface Options
   - Enable Legacy Camera support
   - Enable SSH
   - I6 Serial port: Disable Login Shell, Enable Serial port hardware
   - Ensure one wire communication disabled
   - Enable remote GPIO pins
7. Reboot
8. sudo apt-get update 
9. sudo apt-get install git
10. git clone https://github.com/PetoiCamp/OpenCat.git
11. sudo apt-get install python3-opencv -y
12. sudo apt-get install gstreamer1.0-plugins-base gstreamer1.0-plugins-good gstreamer1.0-plugins-bad gstreamer1.0-plugins-ugly gstreamer1.0-libav
13. sudo apt-get install gstreamer1.0-tools
14. Set up virtual environment for python:
    - sudo apt-get install python3-virtualenv
    - mkdir project
    - cd project
    - python3 -m virtualenv env
    - source env/bin/activate
15. sudo apt-get install pip
16. Install pyserial: pip install pyserial
17. sudo apt-get install python3-tk

# Connect to raspberry pi through ssh
1. Hook the pi up to a monitor and type: ifconfig
2. note the ip address for the pi
3. On your desktop terminal type: ssh pi@the ip address for the pi
4. You will be prompted for the password for the pi. You can now disconnect the monitor from the pi

# Send commands to bittle through ardserial.py via ssh
1. Navigate to the folder: OpenCat/serialMaster
2. type: python3 ardserial.py
3. Now you can enter commands through the terminal

# Start video streaming from raspberry pi to desktop
1. run ifconfig on your desktop terminal
2. enter the desktop ip address in both the sender.py and receiver.py scripts
3. On the desktop, run receiver.py
4. on the pi, run sender.py

# Send files from one machine to another (1st part is file being copied)
1. scp /path/to/local/file username@remotehost:/path/to/remote/directory

# Send entire directory from one machine to another
1. scp -r /path/to/local/directory username@remotehost:/path/to/remote/directory



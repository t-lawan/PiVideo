# PiVideo

In the terminal 

Setup executable file
    - `cd` to this folder (containing the `launcher.sh` file).
    - run 'chmod +x launcher.sh` to make the script an executable

Start test video
    - run `./launcher.sh` to execute the script and play a video
    - Press Crtl-C to stop the script and the video.

Replace the video
    - Add your video file to the folder containing the `launcher.sh` file
    - Edit the `launcher.sh` to add :
        - Change filename on line 5.

Start chosen video
    - run `./launcher.sh` to execute the script and play your chosen video
    - Press Crtl-C to stop the script and the video.

Setup executable file to run on loop and without display status information on screen
    - Edit the `launcher.sh`:
        - Add a comment to line 5
        - Remove comment on line 9
        - To add further options, run `omxplayer --help` or go to this site: https://github.com/popcornmix/omxplayer

Start chosen video on loop
    - run `./launcher.sh` to execute the script and play your chosen video in a loop
    - watch for a couple loops 
    - Press Crtl-C to stop the script and the video.

Create a .desktop File (After your desktop environment starts, it runs whatever commands it finds in the profile's autostart script)
    - run `mkdir /home/pi/.config/autostart`
    - run `nano /home/pi/.config/autostart/video.desktop` to enter file edit mode

Edit .desktop file
    - copy the following into the file
    [Desktop Entry]
    Type=Application
    Name=Video
    Exec= ./home/pi/PiVideo/launcher.sh
    - ensure the path file for `Exec` is correct

Please see the following for further information https://learn.sparkfun.com/tutorials/how-to-run-a-raspberry-pi-program-on-startup#method-2-autostart 
Reboot Pi and wait for the defined time before the video plays.

There are two ways to stop the auto start script.

Before the scripts starts use the terminal 
    - Remove .desktop file
        - run `rm /home/pi/.config/autostart/video.desktop`
    - Comment out the `omxplayer` script in launcher.sh
        - cd to the folder containing the file

Need to write README

Required are package kdialog for the pop-up chooser window, and package ddcutil for the communication with and control of the displays.

To start de switch screen action, and pop-up the kdialog, choose a keyboard shortcut, and in Plasma System Settings create a command like:

Command: echo "SCREEN_1" > /tmp/switch_display_pipe
Name:    Switch Screen 1

and record the keyboard shortcut for the command

Do the same for other displays

To ensure the is started together with the Plasma desktop, copy the script to an convenient directory and add the script the the Plasma System Settings "System > Autostart" settings.

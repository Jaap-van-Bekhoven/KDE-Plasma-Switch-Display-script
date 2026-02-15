SWITCH_DISPLAY

This bash script is configured to run in the background and listen for a keyboard shortcut (one for each configured display). When the keyboard shortcut is pressed, a kdialog window wil start and offer a choice of display inputs.

The script will at startup detect the display(s) and create the configuration required to select the different display inputs. This happens only once at startup, so when an extra display is connected it will not be configured automatically. Fortunately the KDE Plasma Autostart, where the script is integrated in Plasma, makes restarting easy.

Required are package kdialog for the pop-up chooser window, and package ddcutil for the communication with and control of the displays.

To start the switch screen action, and make kdialog pop-up a display input selection Window, choose a keyboard shortcut, and in Plasma System Settings "Keyboard > Shortcuts" create a shortcut command like:

Command: echo "SCREEN_1" > /tmp/switch_display_pipe
Name:    Switch Screen 1

and record the keyboard shortcut for the command

Do the same for other displays

To ensure the is started together with the Plasma desktop, copy the script to an convenient directory and add the script the the Plasma System Settings "System > Autostart" settings.

The script will automatically create the fifo file /tmp/switch_display_pipe, hitting the configured keyboard shortcut will send "SCREEN_1", or "SCREEN_2" to the fifo file and the read loop in the script will pick up the send message and trigger a switch screen action.

<img width="284" height="312" alt="image" src="https://github.com/user-attachments/assets/978bce85-0962-4a1c-a6cb-382ff3749abe" />

Example of a input switch dialog window

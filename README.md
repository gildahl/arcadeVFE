# arcadeVFE 1.2
### The Virtual Arcade Front End
<img width="128" height="128" alt="furry_elephant_vr_arcade_128x128" src="https://github.com/user-attachments/assets/9e708a1a-9422-46ff-91c3-864eef4868a9" />
By David Dahlstrom

Summary
=======
Virtual Reality arcades based on **MAME** such as **Arcade Time Capsule**, do not need conventional front-ends since players walk the floor of the virtual arcade, choosing games just as in real life. So there's no need for game selection menus, pictures and videos of gameplay, or background ambiance sounds since that's already right in front of the player. However, there are still a few important game controller, rom management, and information features common in front-ends that could still be of benefit to VR arcade players--if they could be made to work. This is the gap that **arcadeVFE** seeks to fill.

To this end, **arcadeVFE** includes these features: 

* Ability to automatically execute one or more command line application calls upon the start of each game in the arcade. This can be used to call applications like **Virtual Controller** or other programmable game controller software to create game-specific custom configurations. This makes possible the ability to do anything from tweaking the button layout of a gamepad or fightstick on a per-game basis, combining two or more controllers into one, or building an advanced composite control panel that adjusts to every game in the virtual arcade, just like the sophisticated panels in conventional multicade arcade machines.
* A detailed game information overlay that can be viewed in VR using one's favorite desktop portal. This information comes from the included files, [`history.xml`](https://www.arcade-history.com/index.php?page=download) and [`gameinfo.dat`](https://mameinfo.mameworld.info/), and can also include pictures of your choice--for example, flyers, pcbs, or pictures of real cab control panels (which can be very handy as a reference in the Candy Cab rooms of ATC).
* An arcade machine location directory and editor to more easily locate your favorite machines in the virtual arcade.
* Manual execution of command line actions whenever a particular keyboard key or game controller button is pressed.
* Mapping of controller buttons to keyboard keys in order to, for example, better facilitate access to the **MAME** tab configuration menus while in VR.
* A rom copy feature that can simplify installation of the correct roms into **Arcade Time Capsule**.
* A rom audit feature that can determine whether your rom set is suitable for **Arcade Time Capsule**.
* Voice notification of game control layout changes.
* Automatically run **RawAccel** if you need it.

Resources
=========
* [GitHub:](https://github.com/gildahl/Background-Game-Profile-Switcher) - documentation and source code.
* [Discord:](https://discord.gg/yQ7THG6d2u) - provide comments and report issues. 
* [ATC "Monster" Control Panel Guide:](https://docs.google.com/document/d/1_UpA_Fa-1jQdQMLDDSFTut15gjGnhjljFkd_raw9Ox4/edit?tab=t.0) - build the ultimate ATC control panel.

Tested Software
===============
**arcadeVFE** has been tested successfully with the following software, and is likely able to work with many others:

* [Arcade Time Capsule (ATC)](https://x.com/ArcadeHalf?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor) - fantastic **MAME**-based VR arcade and main tested target of **arcadeVFE**
* [Virtual Controller](https://sourceforge.net/projects/vjoy-controller/) - software to create virtual XInput controllers
* [Ultimarc UltraMap](https://www.ultimarc.com/arcade-controls/joysticks/ultrastik-360-oval-top-clone/) - software to modify behavior of **Ultimarc's UltraStik 360** joysticks
* [Ultimarc JoyTray](https://www.ultimarc.com/arcade-controls/joysticks/servostik/) - software to control ServoStik sticks, including U360 with **ServoStik** upgrade
* [RawAccel](https://github.com/RawAccelOfficial/rawaccel) - software to adjust sensitivity of mouse/trackball controllers

Installation
============
To install arcadeVFE 1.2, follow these four steps:
1. Download the Windows installer from the [Releases](https://github.com/gildahl/arcadeVFE/releases/tag/v1.2.0.0) page.
2. Run the installer and follow the prompts.
3. At the end of the install, accept the option to launch **arcadeVFE**.
4. In the **Initial Setup Dialog** that follows, enter ATC's rom folder in the bottom field, then press **Apply**.
<img width="400" alt="Initial Setup" src="https://github.com/user-attachments/assets/61cc18f0-f2f9-4f76-890e-0013a257179e" />

Before pressing **Close** to complete the installation, you may wish to press the **Audit ROMs** button to perform a quick validation of your rom collection. If you are new to ATC and have not yet installed any roms, you may refer to the next section, [Copy ROMs to ATC](#Copy-ROMs-to-ATC) for a streamlined method of doing this.

>[!NOTE]
> * If you have a previous versions of **arcadeVFE**, you _may_ install 1.2 into the same folder, which will upgrade it; however, it is **strongly** recommended to install 1.2 into a new folder due to the use of a new installer, new defaults, and new plug-in architecture. 
> * arcadeVFE has only been tested with ATC 3.6; however, if you wish to try it with other arcade software, you may chose the **Other** option in the **Initial Setup Dialog** under **Choose your arcade software**, though some features are disabled in this mode. There are also no guarantees on how well it will work, but feel free to report your findings.

Quick Tour
==========
Once you close the **Initial Setup** dialog, you will be taken directly to the **Settings** screen. To confirm proper installation, take a quick tour by performing these actions: 
1. Select a game from the **Choose ROM** list on the top right. You should see its location in the arcade directly beneath. If you ever wish to edit these locations, check the **Edit Directory** checkbox in the **User Preferences** area at the bottom of the screen.
2. With a game selected, press the **Preview GameInfo...** button at the bottom of the dialog. This will display game information that you can navigate through using the left and right arrow buttons. To Exit use the `Escape` key.
<img width="700" alt="Settings" src="https://github.com/user-attachments/assets/4250d53b-ee5a-45b0-86ee-44603fecee74" />

After returning to the Settings screen, you may continue with futher configuration by following the instructions in the [General Configuration](#General-Configuration-(Settings-dialog)) section below.

Note that in the future, whenever you start **arcadeVFE**, you will see nothing immediately on the screen (other than a splash screen), but rather it will create an icon in the Windows Tray indicating that normal background mode is active. Whenever you need to return to the **Settings** dialog, right-click on this icon and choose **Settings...**. You can also click on the **Initial Setup** button in the **Settings** screen to re-invoke the **Initial Setup** dialog to perform audits and rom copy operations.

> [!IMPORTANT]
> _Remember to close the **Settings** screen before you enter your virtual arcade since **arcadeVFE** pauses normal operation while the **Settings** screen is open. If at any time you wisht to exit **arcadeVFE** completely, right-click on its icon in the Windows Tray and select **Exit**._  

Copy ROMs to ATC
================
Use **arcadeVFE** to quickly install the correct roms into **Arcade Time Capsule**, and verify them. 

**Preparation:**
1. Ensure ATC's rom folder is empty: `\Arcade Time Capsule\Retro\VRArcade\Content\Roms`.
2. Fill two source folders with _non-merged_ rom sets. One with roms for mame2010 (0.139) and one with roms for mame2014 (0.159). Don't forget to include the chd subfolders `\kinst` in your 2014 roms folder and `\kinst2` in your 2010 folder.

**Copy the ROMS:**
1. Run arcadeVFE and go to the **Initial Setup** dialog.
<img width="400" alt="Initial Setup" src="https://github.com/user-attachments/assets/61cc18f0-f2f9-4f76-890e-0013a257179e" />
   
3. Ensure the **ROM folder to monitor** field contains a path to the (empty) ATC roms folder on your PC.

> [!TIP]
>  _If you press the **Audit ROMs...** button now, while the folder is still empty, you can get a list of all roms required by ATC and their **MAME** versions._
4. Press the **Copy Roms...** button.
<img width="200" height="165" alt="Copy Roms" src="https://github.com/user-attachments/assets/f18ad5f6-8d6b-4573-8d55-2adb496d7a57" />

5. Choose `2010` as the **ROM version**, and press the **Browse...** button. Browse to the folder containing your 2010 roms, select it, and perform the copy operation when prompted. 
6. Choose `2014` as the **ROM version**, and press the **Browse...** button. Browse to the folder containing your 2014 roms, select it, and perform the copy operation when prompted.
7. Finally, close the **Copy Roms** dialog and press the **Audit Roms** button on the **Initial Setup** dialog to confirm that your rom set is good.

Log
===
See the `log.txt` file in the `\Log` subfolder if needed for troubleshooting. This log is overwritten at the start of every run. Two beeps will be sounded whenever an error is written to the file. When reporting any issues, be sure to include the most recent log with your description of the problem. You may report errors on the Discord.

General Configuration (Settings dialog)
=======================================
**arcadeVFE** offers two different modes of operation. The first is a **ROM Monitor** mode that can execute game-specific actions whenever a game using a **MAME** rom file is played. This mode can provide fully automated game controller configuration in **MAME** environments like **Arcade Time Capsule**. 

The second mode provides the option to trigger actions manually when a game controller button or keyboard key is pressed. Both **ROM Monitor** and keyboard/button actions can be added to the action list in any combination and are simultaneously active whenever the virtual arcade is running. 

ROM Monitor:
------------
To setup a new rom to be monitored, choose `ROM Monitor` from the **Device List** list in the **Settings** screen. Next, choose a rom from the **Choose ROM** list and then use the **Profile** and **Command** fields to configure the specific commands that should execute when that game is loaded. Finally, press the **Assign ROM** button to add your defined command(s) to the **Action List**. 

**Note 1**: If you choose one of the `[Group...]` options in the **Choose ROM** list, you can conveniently assign an action set to a whole group of similarly controlled games. If any of the games in that group need an alternate configuration on an exception basis, simply create another action for that specific rom, which will override the group setting. There is also a `[Default]` action which can be configured for cases where there is neither a rom-specific action nor group action to otherwise handle it.  The following are some examples of Groups.

- `[Group, 4-way]` : assigns the defined action to any game whose native controller is a 4-way joystick.
- `[Group, 8-way]` : assigns the defined action to any game whose native controller is an 8-way joystick.
- `[Group, rotary]`: assigns the defined action to any game whose native controller is a rotary joystick.

**Note 2**: Be aware that **arcadeVFE** is "smart" enough to not execute the same action twice in a row. For example, if you switch between two games that use the same commands (such as two 4-way joystick games that use the same profiles), or exit a game and then restart the same one, profile loading will be suppressed since that configuration should still be in effect.

Buttons and Key Presses:
------------------------
To setup a manual action that will run upon a particular button or key press, Choose `Keyboard` or one of the game controllers from the **Device List** in the Settings screen. Next, use the **Profile** and **Command** fields to configure the command line that will execute when the button or key is pressed. Finally, press the **Assign** button to choose the actual button or key you want to assign to the action and add it to the **Actions List**.

**Note 1**: In addition to command line actions, game controller buttons can also be configured to send virtual keyboard key presses or perform game information screen navigation actions. These options can be configured by choosing the appropriate radio button at the top of the screen whenever a game controller is selected in the **Device List**.

**Note 2**: It is possible to assign multiple actions to the same button or key press, in which case the actions will be invoked sequentially upon each press. See the [Sequence](#Sequence) section below for more information about how this works.

Voice Notification 
==================
If you would like **arcadeVFE** to verbally announce an action when it is executed, you may add a phrase to the optional **Voice notification phrase** field. This is highly recommended as it both provides active feedback that the software is working, and can provide the player with reminders about the control configuration for that game. You can test the phrase to see what it will sound like by pressing the **Voice Test** button. These phrases can provide reminders about how a game is configured. Some example might be:

* "Use left 8 way rotary joystick"
* "Use right 4 way joystick"
* "Use trackball with buttons on left"

How to Configure Command-Line Actions
=====================================
"Profiles", as defined in this document, are files containing specific game controller configurations created by game controller configuration software. Examples of such files might be `U360.vcd` for **Virtual Controller**, or `4-way.ugc` for **UltraMap**. To make command creation easier, you may specify the file name of a profile separately in the **Profile** field, and then choose a command template in the **Command** field, into which the profile will be inserted when the **Assign** button is pressed. This template will typically contain one of the following field tags:

- `[profile_name]`        - will be replaced by the filename or contents of the **Profile** field
- `[profile_full_name]`   - will be replaced by the full path/file or contents of the **Profile** field

For example, if the profile is `C:\Ultrastik\Profiles\qbert.ugc` and the command line template is `C:\UltraMap\UltraMap.exe [profile_name]`, then upon pressing the **Assign** button, the command line that will be assigned to the action will be `C:\UltraMap\UltraMap.exe qbert.ugc`. If the full path to the profile is needed, then the command line template should be changed to `C:\UltraMap\UltraMap.exe [profile_full_name]`. If the command line template has no field tags, then the command line will be used verbatim with no insertions. 

Additional Notes:
-----------------
* To test a command line while still in the **Settings** screen, press the **Test** button next to the Command field. Hovering over the **Test** button with the **Show Tooltips** option turned on, will show the actual command line that will be executed.

* If your profile filename needs quotes around it, then simply add quotes around the field tag in the template, such as `"[profile_name]"` or `"[profile_full_name]"`.
 
* If you wish to trigger two or up to three commands in a single action, click on the checkbox next to **Profile 2** and/or **Profile 3** and you can configure a second and/or third command line using a completely different profile and command line template.

* If you want to add a new template to **arcadeVFE** that will persist across sessions, you can edit any of the built-in ones and then use the **Add** button. You may also delete any template you no longer want to see in the list.  Note that whenever you do this, all three **Command** lists will be synchronized to contain the same list of templates.

* As an FYI, these templates are saved in a file called `templates.json` in the root VFE folder. You may delete this file to restore the original defaults.

> [!IMPORTANT]
> _Be aware that VFE pauses active operation while the **Settings** screen is open, so be sure to close it when done with configuration._

Understanding the Action List Table
===================================
Each time you use the **Assign** button to create a new action, that action will be added to the **Action List** table. If you get a warning saying "Duplicate", **arcadeVFE** will highlight the duplicate action in the list at which point you may delete it and try again or keep it.

When you complete the table, press the **Save list** button to save it.  It will be saved in the `\User` folder as a `*.json` file having the name specified in the **Activity list name** field above the table. By default this name is `Arcade Controller` (saved as `Arcade Controller.json`). If you switch between multiple controllers for use with your emulator, you could save different action lists under different names. These can then be loaded in the future by creating a shortcut that provides the name as a command line parameter when launching VFE.  For example,

* `>vfe.exe "Arcade Controller"` or
* `>vfe.exe "Gamepad"`

## The Action list table contains the following columns:

### Device List
The device or method that was chosen to trigger the action.

### Action
* For the `ROM Monitor` Device List option, this column shows the rom you chose to monitor.
* For the `Keyboard` Device List option, it shows the keyboard key or key combo you assigned.
* For a game controller, it shows the button number or other control input you assigned.

### Sequence
For `Keyboard` and game controller actions, it is possible to assign multiple actions to the same key or button. The effect of this is that when you press that key or button the first time, the action with a sequence number of 1 will be triggered. When you press that same key or button a second time, the action with a sequence number of 2 will be triggered, and so forth (with each action being verbally announced if you provided notification phrases with each). This provides a means to manually switch between multiple profiles using a single key or button. 

**Sequence numbers** are assigned to each action automatically when you add the action. To change the auto-assigned sequence of an action, just use the **Move Up** and **Move Down** buttons and you will see the sequence number for that action adjust according to its position in the list. Note that for `ROM Monitor` actions, the sequence number will always be 1 (since these are fully automated actions that have no need for sequencing).

### Voice Phrase
This is the voice notification phrase you assigned to the action.

### Command
This is the command line template with field tags replaced (i.e. the actual command line that will be executed).

### Command 2 and Command 3
These are the second and third optional command line templates with field tags replaced (i.e. the actual command lines that will be executed).

## Managing the Action List table
Below the **Action List** table are several additional buttons with the following functions:

### Move Up / Move Down
These buttons are intended for use in changing the sequence order of actions assigned to a single button or key press as described above under [Sequence](#Sequence). 

### Clear all
This clears the entire table (if you press this by mistake, just close the screen without saving and re-open it).

### Copy action
Copies fields from the selected row back into the editor fields to ease the creation of similar entries.

### Delete action
Removes the selected row from the table.

### Save actions
Saves all actions in the table to the `User\<action list name>.json` file. 

User Preferences
================
These options allow the user to make adjustments to certain features.

### Monitor only when the arcade is running
This is a recommended setting for most use cases (and required for the **Run RawAccel** and **Use GameInfo Overlay** options). Turning this off is mainly intended for testing and can cause side-effects in other applications. Note that you will need to exit and restart **arcadeVFE** if you change this setting.

### Always voice notify
If you have configured voice notification phrases for your actions, then this switch can control when these are heard. This checkbox has three states. When checked (the default), the voice will be heard every time a game referenced in the action table is run. When unchecked, voice notification is effectively turned off. Finally, if the checkbox is configured with the minus sign (-), then voice notification will only occur if an action was actually executed (see the **Note 2** in the [ROM Monitor](#ROM-Monitor) section above).

### Beep on action
This option will sound a beep whenever a command action happens. This can be useful as a debugging tool by asserting profile changes independent of the voice option.

### Edit Directory
This option will enable the edit controls under the Choose ROM list containing the locations of arcade machines in the virtual arcade. You may edit these as you please. 

### Run RawAccel
**RawAccel** is a utility that can be found on GitHub at `https://github.com/RawAccelOfficial/rawaccel`. This software may be needed to tune some trackballs to have additional sensitivity. For example, I need it to make my **Ultimarc U-Trak** trackball work correctly in **Arcade Time Capsule**. To integrate **RawAccel** with **arcadeVFE**, simply install it to a subfolder of VFE called `..\RawAccel`.

This option is only available when the **Monitor only when the arcade is running** above setting is configured. When this option is turned on VFE will automatically load **RawAccel** when the arcade is running, and will close **RawAccel** when the arcade is closed. It is up to the user to configure **RawAccel** properly for their trackball before use. 

### Show Tooltips
In addition to this documentation file, the **Settings** screen implements tooltips on all controls to explain their operation. If you no longer need the tooltips, you can turn them off by unchecking the **Show Tooltips** checkbox.

### Use GameInfo Overlay
This feature will display an overlay monitor showing detailed game information, including pictures, associated with the game currently running in the arcade. This information may be easily viewed while you are in VR by using your favorite desktop viewport (third party, or one provided with your headset). The text information comes from the `mameinfo.dat` and `history.xml` files in the `\GameInfo` folder. This overlay will automatically unload when the arcade is closed (which is why this feature is only available when the **Monitor only when the arcade is running** setting is configured).

To navigate through the **GameInfo** screens, you will want to assign at least the `Right` action in the game controller button configuration (and optionally, the `Left`, `Start`, and `Exit` options), using the **GameInfo navigation** radio switch at the top of the screen. If you would like custom pictures to be displayed along with the text information, you may create additional folders within the `..\GameInfo\Assets` subfolder of **arcadeVFE**, and fill it with `*.jpg` or `*.png` files having root names that are the same as the roms you would like to associate them with. Examples are provided in the `..\GameInfo\Assets\cabinets` folder along with a few others. Feel free to add additional folders as you like.

#### Font Size
Set the font size used in the **GameInfo** screen. If you revise the font size, you may preview it by pressing the **Preview GameInfo...** button.

#### Choose Monitor
If you use mouse clicks as a fire button, these will not work if the overlay is covering the emulator's screen. One way to address this is to move the overlay to another screen if you have one. To do this, just change this setting to present the **GameInfo** on a different monitor. See @2 in the [Limitations](#Limitations) section below for more information about this.

vfe.ini Settings
================
Most of the settings stored in the `.\Config\vfe.ini` file are set in the user interface, so most users will never need to access or modify this file directly. However, there are a few settings that can only be changed in this file that some users may have an interest in. All of these are in the `[GameInfo]` section.
1. `ImageOrder=`: To change the order that images are displayed in **GameInfo**, you may modify the comma separated string containing the image subfolder names found in `.\GameInfo\Assets. Having extra or missing folders in this list is allowed.
2. `HideCursor=`: To hide the mouse cursor when displaying the **GameInfo** screen, you may change this value from 0 to 1.
3. `SettingsExitKey=`, `SettingsRightKey=`, and `SettingsLeftKey=`: These may be used to change the keys that are used for navigation in the **GameInfo** screen when it is accessed via the **Preview GameInfo...** button. Note that this does not change the keys/buttons that are used during gameplay as those are set as **Actions** in the **Actions List**.

Limitations
===========
Because this software is not code-integrated with the host emulator, but relies on external interop techniques, there are a few limitations that should be noted. These may rarely be noticed, but they are good to be aware of.

1. **arcadeVFE** can only tell when a new game is loaded, but not when it is exited. Therefore, it can only surmise that you have exited a game when it detects that you have started a new and different game. Consequently, if you exit a game and re-enter the SAME game, **arcadeVFE** will not know that you did this. This should not affect practical operation since whatever state was loaded when you originally started the game will still be in effect. However, **arcadeVFE** will not be able to provide feedback (such as a beep or voice notification) when restarting the game. Only upon starting a new game.

2. The **GameInfo** window that **arcadeVFE** overlays on top of the virtual arcade desktop display is specifically designed to not take the focus. However, as an overlay it still has the effect of preventing mouse clicks from passing through to the application (whether or not you are actually viewing it). The consequence is that if you use the mouse button as a fire button in some games, it may not work while using the **GameInfo** feature. The solution to this is to either keep the **GameInfo** feature turned off, or ensure that you map a (non-mouse) game controller button as your fire button. Another solution, if you have two or more monitors, is to simply move **GameInfo** to another monitor by using the **Monitor** option in **User Preferences**. This will prevent the overlay from blocking ATC while displayed and should allow the mouse to work as expected.   

3. **arcadeVFE** pauses operation while the **Settings** screen is displayed. Therefore, if you open your arcade software while the **Setting** screen is open, **arcadeVFE** will not perform any monitoring. If this happens, close both your arcade software and **arcadeVFE**, then restart.

4. **arcadeVFE** does not actively monitor for new game controllers while running. So be sure that any game controller(s) you intend to use with it are plugged in before you start the software. If you turn-on/plug-in a controller while the software is running, the controller will not be recognized until you restart the software.

# MGZSEV-UK-Torque-Pro-PIDS

Instructions for installation and use of the Version 2 PIDs.

These PIDs were derived from Peter Nixon's fantastic work (on Github) and supplemented with others from the OVMS group spreadsheet, the Thai app, and a good few of my own too. They are setup to work correctly with UK BMS Versions and developed for the UK ZSEV standard car using miles, mph and m/kwh units etc. Please note that some of the PIDs in the file are not meant to be displayed, they are used by other PIDs in their calcs (see below for details). The PIDs are continually being developed so check back often for more info.

Download Torque Pro (the paid version) to you phone from the Play Store.  Torque Pro is not available for Apple Phones.

Download all the files in this repositay MGZSEV UK PIDs VerXX.csv file from the “Files” section of this group to your phone (downloads).

Download the MGZSEV Torque Dash Settings VerXX.dash file from the “Files” section of this group to your phone (downloads).

In your Android phone File Manager go to settings and make sure "show hidden files" is ticked and then find the .torque (note the dot at the front) folder.  In this folder you will use the “extendedpids” folder and the “dashboards” folder.

The first thing to do in the Torque Pro app is to select the correct OBD2 protocol for the MGZSEV, this will make the initial comms connection much faster. From the initial screen in Torque Pro press once on the blue "Profile..." text and then select the blue edit icon. Scroll right to the bottom of the profile and in the Preferred OBD2 Protocol area select the ISO 15765-4 CAN (11bit 500k baud) setting.

Now let’s clean up and delete the old data and files we no longer need in Torque Pro: 
1.	Open the Torque Pro app and go to the main screen settings (bottom left), select "Manage extra PIDs/sensors" then click the 3 dots at the top right of the next screen that lists all the current PIDS being used, we don’t need any of these). Select "Clear list" from the menu, this will clear all of the old PIDs and give you a clean screen.
2.	In the “Realtime Info” area Delete all the old gauges in all the pages, these are not used.
3.	In File Manager navigate to the “extendedpids” folder and delete all the files except “other”, then navigate to the “dashboards folder” and delete the files in there too. 
Import the new PIDs and Dashboard:
1.	Copy the MGZSEV UK PIDs.csv file you downloaded (in your downloads folder) into the “extendedpids” folder.
2.	Copy the MGZSEV dash settings.dash file you downloaded (in your downloads folder) into the “dashboards” folder.
Setup the Torque Pro app to use the new PIDs:
1.	In the “Realtime Info” screens (which should be all blank) click settings, Layout Settings, then Import Settings.  Import the new “MGZSEV Torque Dash Settings”.
2.	In Torque Pro’s initial screen select the main settings, then select “Manage extra PIDs/sensors”.  In the next screen select the 3 dots at the top right and select “Add pre-defined set”, choose the new MGZSEV UK PIDs file.

Torque Pro should now be set up ready to connect to your MGZSEV.

Start up the car into READY mode and then connect Torque Pro via Bluetooth to the OBD2 connector plugged into your OBD socket.  After the Bluetooth connects the app will take about 15 sec to connect to the car and start to show data.

Torque Pro will automatically detect you BMS version and apply the correct formulas and equations in the PIDs for your UK standard. If it doesn’t recognise your BMS version (let me know) then it will apply the latest standard that it knows of by default.

The SoC has been corrected for the BMS software version detected and will show 100% when fully charged and balanced and 0% when empty.

The Range display takes into account the remaining SoC, the outside air temp, the SoH for your battery pack and the reference m/kwh set for an average 25 C summer day (default is 3.8 m/kwh).  This shouldn’t be set to the best value you’ve got in the summer, but a good normal value that you know you can easily achieve.  There are 2 Range displays to choose from, the default is for those who travel at 60mph max on motorways and the second is for those who travel at 70mph max on motorways. The app will also show you the overall Target m/kwh required to achieve that range.

The Charge/Discharge gauge shows you the rate of Charge/discharge in use or during charging on a rapid (car in READY mode). + is charging and – is discharging.

The next screen shows tyre pressures in psi.  It also has a “charger to charger” range display which shows the maximum miles to plan between rapid chargers assuming you leave the charger at 85% and arrive at the next with 15% SoC.

This screen also shows the BMS SW version part number.  Mine is R17 which is the old pre faulty BMS standard giving 456v after full balance charge. Your will probably be EU1 or A01.

The Balance Error display shows you the average balance error between the 9 CMU packs and is calculated the same way as MG do it. If its below 0.100 then according to MG its ok, but the lower it is the better.  If it’s approaching 0.100 then you should do a balance charge.

The “Cons 60” display on the second page allows you to change the reference consumption used for the Range displays.  It’s set to 3.8 m/kwh by default to reflect the average normal consumption for a 25 C summers day.  You can change this to whatever you think is better for you, but 3.8 gives me a pretty accurate Range display for my driving style mixed motorway (60mph) and A roads. Its much more accurate than the GoM in the car. Changing this value will also change the 70mph value respectively.

A further screen shows each of the 9 CMU packs balance error difference (Max V minus Min V) and the average of all 9 (which is how MG say it should be calculated).

Please note that only the PIDS that start with MGZSEV should be used if you’re going to create your own displays, the other PIDs starting with XX are not intended for display and are either used for calculations or not currently used.

You can watch the “setup and how to use” video here:   https://youtu.be/ldwumUZj8VE


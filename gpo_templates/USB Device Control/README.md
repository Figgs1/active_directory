# AD GPO Template for USB Device Control on a Budget

There are many ways to either explicitly block or allow USB device access, but creating a granular process becomes difficult without another point solution or agent deployed to the client.  Below is a list of directions that can be used to create a whitelist of USB devices for your organization.

## USB Device Control Steps:

1.	Download the devcon executable from https://docs.microsoft.com/en-us/windows-hardware/drivers/devtest/devcon.

2.	Once installed, copy devcon.exe to %sysdir%, and from an elevated command prompt, run devcon (as described below) against a local PC, a remote PC, or a list of PC's leveraging PSExec.

        Local:
        To pull a list of all HwIds:
        devcon hwids * >>c:\computer_hwids.txt
        To pull a list of all USB HwIds:
        devcon hwids =usb >>c:\computer_hwids.txt

        Remote:
        To pull a list of all HwIds:
        devcon /m:\\computer hwids * >>c:\computer_hwids.txt
        To pull a list of all USB HwIds:
        devcon /m:\\computer hwids =usb >>c:\computer_hwids.txt

        Against a List:
        Create a text file with a list of hostnames on the root of C:\ called hostnames.txt.  Next, copy the commands below to a separate text file, give it a name and save with a .bat file extension:

        For /F %%A in (c:\hostnames.txt) do (
        Psexec \\%%A devcon hwids =usb >>c:\computer_hwids.txt
        )

3.	Once the hardware ID's are collected, scrub the list and remove all metadata and labels from the created lists, leaving only the hardware ID strings.

4.	Next, create a new Active Directory Group Policy Object.

5.	Use the following article as a reference:  https://msdn.microsoft.com/en-us/library/bb530324.aspx#grouppolicydeviceinstall_topic5ba

6.	To open Group Policy Object Editor, click the Start button, type mmc gpedit.msc in the Start Search box, and then press ENTER.

7.	In the Group Policy Object Editor navigation pane, click Computer Configuration->Administrative Templates->System->Device Installation, and then open Device Installation Restrictions.

8.	In the details pane, right-click Prevent installation of devices not described by other policy settings, and click Properties.

9.	The policy dialog box appears with the current settings.

10.	On the Setting tab, click Enabled to turn the policy on.

11.	Click OK to save your settings and return to Group Policy Object Editor.

12.	Next, in the details pane, right-click Allow administrators to override device installation policy, and then click Properties.

13.	The policy dialog box appears with the current settings.

14.	On the Setting tab, click Enabled to turn the policy setting on.

15.	Click OK to save your setting and return to Group Policy Object Editor.

16.	Both policies now show their state as enabled.

17.	Now, define the USB device whitelist settings.

18.	In the Group Policy Object Editor navigation pane, click Computer Configuration->Administrative Templates->System->Device Installation, and then open Device Installation Restrictions.

19.	In the details pane, right-click Allow installation of devices that match any of these device IDs, and then click Properties.

20.	The policy dialog box appears with the current settings.

21.	On the Setting tab, click Enabled to turn on this policy

22.	Click Show to view the list of allowed devices in the Show Contents dialog box. (By default, the list is empty.)

23.	Click Add to open the Add Item dialog box.

24.	Enter the device ID(s) for your device(s).

25.	Click OK to return to the Show Contents dialog box. Your device(s) now appear in the list.

26.	Click OK to return to the policy dialog box, and then click OK to save your new policy setting.

27.	To allow USB device installation while requiring a blacklist of specific, unapproved devices, follow the steps listed here:  https://msdn.microsoft.com/en-us/library/bb530324.aspx#grouppolicydeviceinstall_topic7


# To test the effects of your restriction settings as a user:

1.	If your device is installed, uninstall and remove it by following the steps in the Uninstalling your USB memory drive.

2.	Click the Start button, type gpupdate /force in the Start Search box, and then press ENTER.

3.	When the gpupdate command has finished, log off of your computer, and then log back on.

4.	To open Device Manager, click the Start button, type mmc devmgmt.msc in the Start Search box, and then press ENTER.

5.	Plug in your USB memory drive.

6.	Until the installation is completed successfully, the device appears in Device Manager under the Other devices node.

7.	If you are logged on as a standard user without administrative rights, because device installation is now restricted, a dialog box will appear prompting you to enter administrative credentials.

8.	To simulate a typical user response, click Locate and install driver software (recommended).

9.	A variant of the User Account Control dialog box appears, asking you for a user name and password for an account that has administrator rights.

10.	Click Cancel to abort the attempt as an unprivileged user would do.

11.	The device driver installation fails, and the device remains under the Other devices node and is not functional.


# To test the list of authorized devices:

1.	Click the Start button, type gpupdate/force in the Start Search box, and then press ENTER.

2.	When the gpupdate command has finished, log off of your computer, and then log back on.

3.	To open Device Manager, click the Start button, type mmc devmgmt.msc in the Start Search box, and then press ENTER.

4.	Click OK to close the message. Device Manager will start and you can view the devices in the computer.

5.	Plug in your USB memory drive.

6.	The device appears in Device Manager under the Other devices node until Windows completes the installation.

7.	After Windows completes the installation, the device moves to the Disk Drives node in Device Manager and is fully functional.

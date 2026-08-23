# FL Studio Linux Setup Guide
#### Unofficial setup guide for running FL Studio on Linux using Bottles (wine)

Flathub setup: https://flathub.org/setup

Bottles: https://usebottles.com/

Bottles on Flathub: https://flathub.org/apps/com.usebottles.bottles

Flatseal: https://flathub.org/apps/com.github.tchx84.Flatseal

Kron4ek wine releases: https://github.com/Kron4ek/Wine-Builds/releases 

## Notes / Updates:
- (Aug, 2026) WARNING : FL Studio 26.1.4 has a new cert that breaks FL Studio as Wine is unable to verify with WinTrust. `WINTRUST_DefaultVerify returning 80096004`. For the meantime use FL Studio 26.1.3 or lower until Wine has the fix applied.
- (Jan, 2026) WARNING : FL Cloud Plugins appears to have a memory leak.


## Installing Runners
In Bottles, wine distributions are called Runners. There are quite a few to choose from. Many users have had the best success with `Soda`, `Kron4ek` or `Proton GE` in the Runners menu. You may need/want to enable Pre-Release versions under General -> Advanced in order to get newer/other versions of wine runners.

<img width="349" height="296" alt="Preferences" src="https://github.com/user-attachments/assets/5e06d028-29e4-45e5-afe2-ebadd2586520" />

<img width="862" height="626" alt="RunnersMenu" src="https://github.com/user-attachments/assets/6d9b96e9-71bd-443a-9320-1e255827e669" />

## DLL Components
I use DXVK and VKD3D in my bottles. They can be found in the `DLL Components` menu tab to the right of `Runners` and `Cache`

## First Bottle
After getting familiar with the Bottles program, create a new bottle. Choose a name for the bottle and select a runner (ideally one we installed in the previous step `Installing Runners`. The following screenshot shows the drop down for Runners with `ge-proton10-25` selected.

<img width="584" height="720" alt="Screenshot From 2025-12-04 17-18-46" src="https://github.com/user-attachments/assets/b6537b71-8de6-455d-98fd-9001556b6764" />


#### Dependencies
In the new bottle scroll down to Options to find Dependencies and once inside install the "allfonts" dependency. This will pull in many common fonts.
![image](https://github.com/user-attachments/assets/e0144902-aa32-484d-8892-1da281674a91)

We will want to add the msgothic font file. This will allow rendering musical notation symbols such as sharps and flats. We can download that file from here https://github.com/FSKiller/Microsoft-Fonts/blob/main/msgothic.ttc

In the Bottle's main Details page, click the Browse button to open the bottle's `C:/` drive. Then navigate to `/windows/Fonts` and place the file `msgothic.ttc` there.

<img width="617" height="350" alt="BrowseCDrive" src="https://github.com/user-attachments/assets/451784be-1473-480e-98f4-19ebb480d9f5" />

#### Settings
Confirm the Runner, DXVK and VKD3D settings are as expected. 
<img width="600" height="370" alt="Settings" src="https://github.com/user-attachments/assets/ea90bdb7-dbf2-4f23-908d-2c6b5b28df8d" />

I set the Windows Version to Windows 11 down in Compatibility. 
![image](https://github.com/user-attachments/assets/34690ff1-da03-4f28-a8ff-1af85dbbe9a3)

## Install FL Studio
Download the windows exe installer from Image Line https://www.image-line.com/fl-studio-download/

In the bottle, Run Executable and find the exe and run it.
<img width="616" height="166" alt="RunExe" src="https://github.com/user-attachments/assets/344a1d3f-1afc-43e5-b110-939bf151f597" />

I do not install the FL plugin (64bit). 

If you don't plan to test/use FL Cloud Plugins then don't worry about installing that either.

The installer for WebView2 can take some time. This is expected.

After the installer completes (you may need to go back to the main Bottles menu and back into the FL Studio bottle) you will see FL64 in the Programs list. Here is a bottle with FL Studio Beta and RC for testing installed:
<img width="628" height="497" alt="BetaInstalledPrograms" src="https://github.com/user-attachments/assets/ebb94ba9-a831-4799-b76d-1f173119dd5c" />


#### Notes:
- If the installer does not startup the first time after creating the bottle, restarting the bottles application and trying again "fixed" this for me.

## First Run
The first time you open up FL Studio it will be in Trial mode. It may take a moment to load the first introduction project. 

For me, there are some goofy "FAIL" messages regarding midi input.

![image](https://github.com/user-attachments/assets/079cec4c-9be3-4bee-b15b-8bd02a3531db)

I just disable these.

If everything seems good enough, we can register! I login with credentials. On GNOME we can set up a desktop file so the web redirect works for login, but this is easier.

![image](https://github.com/user-attachments/assets/d4bea109-57d1-46ca-943a-1c543d933b3c)

Your computer may warn you that bottles is not responding when you enter the validation code on GNOME. I press wait and it does succeed for me. The usual popup to restart after validation will show up and I restart without saving.

![image](https://github.com/user-attachments/assets/10e3f29a-d00e-4787-a3f7-587980b14685)


## Next Steps
It will be very beneficial to install [Flatseal](https://flathub.org/apps/com.github.tchx84.Flatseal). It is a graphical tool for modifying permissions and settings for Flatpak installed applications (such as Bottles). 

Some things I did with Flatseal:
- Adding Filesystem entry `xdg-music` to be able to work more easily with content between different bottled versions of FL Studio.
- Adding Filesystem entry `xdg-data/applications` so that I can "Add Desktop Entry" for FL Studio in GNOME.
- Updating the `.desktop` entry to include `MimeType=x-scheme-handler/flstudio` will allow authenticating from a browser (that supports xdg-open). I have not been able to do this with Firefox in Flatpak, but Chromium in flatpak works.

## Other
I hope this guide is helpful and can be expanded to assist folks in running FL Studio in linux based operating systems.

Please remember FL Studio is not officially supported on Linux and there may be many features that are unaccessible for various reasons. This guide is intended to explain how I personally use FL Studio in an unofficial and unsupported way. 

If you have any corrections, tips, tricks, or expanded information for running FL Studio in wine I would very much appreciate issues/requests to enhance this guide. I will update as new information is available.

#### WebView2 information
- https://github.com/MicrosoftEdge/WebView2Feedback/issues/3127
- https://appdb.winehq.org/objectManager.php?sClass=application&iId=20379

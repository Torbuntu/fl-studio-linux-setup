# FL Studio Linux Setup Guide
#### Unofficial setup guide for running FL Studio on Linux using Bottles (wine)

Flathub setup: https://flathub.org/setup

Bottles: https://usebottles.com/

Bottles on Flathub: https://flathub.org/apps/com.usebottles.bottles

## Installing Runners
In Bottles, wine distributions are called Runners. There are quite a few to choose from. I have been using the Kron4ek builds with staging.

#### Notes: 
- As of Apr 5th, 2025 I recommend using 10.1 if you use Kron4ek. Anything newer seems to cause broken links for the user directory.
- You may need/want to enable Pre-Release versions under General -> Advanced.

## DLL Components
I use DXVK and VKD3D in my bottles.

## First Bottle
After getting familiar with the Bottles program, create a new bottle. 
![image](https://github.com/user-attachments/assets/07eac712-cebd-4ae8-b483-a8f4be6a6ae2)

This Bottle will use the name "FL Studio" and use the Application setting. The Runner will be set to "kron4ek-wine-10.1-staging".

#### Dependencies
In the new bottle, under Dependencies, install the "allfonts" dependency. This will pull in many common fonts.
![image](https://github.com/user-attachments/assets/e0144902-aa32-484d-8892-1da281674a91)

We will want to add the msgothic font file. This will allow rendering musical notation symbols such as sharps and flats. We can download that file from here https://github.com/FSKiller/Microsoft-Fonts/blob/main/msgothic.ttc

In the Bottle's main Details page, click the three dot menu in the corner and Browse Files.
![image](https://github.com/user-attachments/assets/3eb52973-7e4a-43e5-92e9-b8bf471b97a6)

Move the font file here `drive_c/windows/Fonts/` 


#### Settings
Confirm the Runner, DXVK and VKD3D settings are as expected.
![image](https://github.com/user-attachments/assets/1577a7db-31de-4d62-866f-66cd5b166519)

I set the Windows Version to Windows 11 down in Compatibility. 
![image](https://github.com/user-attachments/assets/34690ff1-da03-4f28-a8ff-1af85dbbe9a3)

## Install FL Studio
Download the windows exe installer from Image Line https://www.image-line.com/fl-studio-download/

In the bottle, Run Executable and find the exe and run it. This runs how one should expect.

I do not install the FL plugin (64bit). 

If you don't plan to test/use FL Cloud Plugins then don't worry about installing that either. As of writing this, nothing using WebView2 works anyway (Apr, 5, 2025).

After the installer completes (you may need to go back to the main Bottles menu and back into the FL Studio bottle) you will see FL64 in the Programs list.
![image](https://github.com/user-attachments/assets/7e340fca-6f27-429c-a1dd-7d79a948789a)

#### Notes:
- If the installer does not startup the first time after creating the bottle, restarting the bottles application and trying again "fixed" this for me.

## First Run
The first time you open up FL Studio it will be in Trial mode. It may take a moment to load the first introduction project. 

For me, there are some goofy "FAIL" messages regarding midi input.
![image](https://github.com/user-attachments/assets/079cec4c-9be3-4bee-b15b-8bd02a3531db)

I just disable these.

You will also likely notice that the Sounds tab in the left browser window is black. This is from WebView2 being broken currently and means we will not have access to FL Cloud currently. 
![image](https://github.com/user-attachments/assets/371062b9-536a-4670-be33-7ee7639768e5)

Due to this, and to prevent unknown issues, I "hide" that tab (right click -> hide).

If everything else seems good enough, we can register! I don't know how to currently get the unlock with web to work, so I use my account login still:
![image](https://github.com/user-attachments/assets/d4bea109-57d1-46ca-943a-1c543d933b3c)

Your computer may warn you that bottles is not responding when you enter the validation code. I press wait and it does succeed for me. The usual popup to restart after validation will show up and I restart without saving.
![image](https://github.com/user-attachments/assets/10e3f29a-d00e-4787-a3f7-587980b14685)

#### Notes: 
- You may have to hide the sounds tab again after registering.


## Other
I hope this guide is helpful and can be expanded to assist folks in running FL Studio in linux based operating systems.

Please remember FL Studio is not officially supported on Linux and there may be many features that are unaccessible for various reasons. This guide is intended to explain how I personally use FL Studio in an unofficial and unsupported way. 

If you have any corrections, tips, tricks, or expanded information for running FL Studio in wine I would very much appreciate issues/requests to enhance this guide. I will update as new information is available.

#### WebView2 information
- https://github.com/MicrosoftEdge/WebView2Feedback/issues/3127
- https://appdb.winehq.org/objectManager.php?sClass=application&iId=20379



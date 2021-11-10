# Mobile Forensics: AFLogical OSE
44386-01 Digital Forensics \
Demoed By: Mackenzie Bishop
# AFLogical OSE
Free software for use by non-law enforcement personnel and forensic analysists. It allows an examiner to extract call logs, contacts, MMS messages, and SMS messages from Android devices. More information available at: https://www.nowsecure.com/

# Installation + Santoku-Linux
Download the [latest apk](/nowsecure/android-forensics/downloads) or use santoku linux (AFLogical OSE comes pre-installed) \
Copy the apk to your device and run it or use a command shell and run the script below. \
Example:```adb install AFLogical-OSE_1.5.2.apk``` \
\
Here is a screenshot of the files after they were downloaded via the download link: \
![image](https://user-images.githubusercontent.com/69914681/141058577-6f8c9c23-ed6d-4525-9117-ba170a2682df.png) 
During a test run, I tried emailing the APK file to my phone and Outlook would let me download the file but wouldn't allow me to open it, stating that "Outlook doesn't download APK files to avoid security risks".

Set up your phone in developer mode: Settings > About phone > Software information > tap "Build number" several times > enter your PIN to enable Developer options menu \
\
Settings > Developer options > enable USB debugging \
\
Using Oracle VM VirtualBox: \
\
![image](https://user-images.githubusercontent.com/69914681/141066100-8012e50a-bf50-4dce-8152-eb4da0d02a96.png)\
Devices > USB > Select device name \
\
Start AFLogical OSE in Santoku-Linux in VirtualBox: \
\
![image](https://user-images.githubusercontent.com/69914681/141066412-432db580-a2b7-4bbe-8892-ad9e077e9615.png)\
\
When prompted, enter the following commands into the shell: \
```abd devices```
\
```aflogical-ose```\
\
Enter your password after connecting your Android device to a USB cable. After the build is successful, press enter to pull the data to the SD card stored in the Android device.\
\
After moving the APK file to my phone via USB cable, I was able to install it as an application. After launching the app, select all boxes available and select 'Capture'. In VirtualBox, press enter to pull the data from the SD card stored in the Android device to the VM directory.\
\
The files typically save as .csv and .xml files, making them easier to navigate and sort through using Excel.

# Notes
* AFLogical OSE doesn't recover deleted messages from an Android device. To recover deleted files, you would need to pull the .db file and use a separate tool (Scalpel, FTK, Encase) to carve for deleted data. 
* Tutorials that I could find for this software ranged anywhere from 2 to 7 years old.

# Resource Links
Santoku-Linux Guide for AFLogical OSE: https://santoku-linux.com/howto/howto-use-aflogical-ose-logical-forensics-android/ \
Youtube tutorial for AFLogical OSE with Santoku-Linux 0.5: https://www.youtube.com/watch?v=1l6RUjK09bU \


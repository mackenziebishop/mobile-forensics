# Mobile Forensics: AFLogical OSE
44386-01 Digital Forensics \
Demoed By: Mackenzie Bishop
# AFLogical OSE
Free software for use by non-law enforcement personnel and forensic analysists. It allows an examiner to extract call logs, contacts, MMS messages, and SMS messages from Android devices. More information available at: https://www.nowsecure.com/

# Installation
Download the [latest apk](/nowsecure/android-forensics/downloads) or use santoku linux (AFLogical OSE comes pre-installed) \
Copy the apk to your device and run it or use a command shell and run the script below. \
Example:```adb install AFLogical-OSE_1.5.2.apk``` \
\
Here is a screenshot of the files after they were downloaded via the download link: \
![image](https://user-images.githubusercontent.com/69914681/141058577-6f8c9c23-ed6d-4525-9117-ba170a2682df.png) 

# Using Santoku-Linux


# Notes
* AFLogical OSE doesn't recover deleted messages from an Android device. To recover deleted files, you would need to pull the .db file and use a separate tool (Scalpel, FTK, Encase) to carve for deleted data. 
* Tutorials that I could find for this software ranged anywhere from 4 to 7 years old (rip) - the software seems pretty outdated.
# Resource Links
AFLogical OSE Repo for Download: https://github.com/nowsecure/android-forensics \
Santoku-Linux Guide for AFLogical OSE: https://santoku-linux.com/howto/howto-use-aflogical-ose-logical-forensics-android/ \
Youtube tutorial for AFLogical OSE with Santoku-Linux 0.5: https://www.youtube.com/watch?v=1l6RUjK09bU

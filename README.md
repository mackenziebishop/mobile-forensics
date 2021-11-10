# What is Whatsapp Xtract?
Whatsapp Xtract is a tool that has been created to display Whatsapp chats on your pc using the backup database files from your android device. This makes it easier to search through all messages you have sent and according to the author:
- gives you access to a useful backup of your whatsapp chats.
- be able to read your whatsapp chats again using a backup file
- delete the grown-too-big message history of whatsapp without losing the possibility to read the old conversations.
- read older messages without the need of endlessly pressing the annoying "load older messages" button.
- be able to search old messages.
- ...

This is a tool made by Fabio Sangiacomo and ztedd and improved by many others.
A link to this project is available here: https://forum.xda-developers.com/t/tool-whatsapp-xtract-backup-messages-extractor-database-analyzer-chat-backup.1583021/ 


# Prerequisites
In order to use the tool we will need a couple of files:
- Database file (mgstore.db)
- Key encrypt file (key)
- Names corresponding to phone numbers (wa.db)
- The tool itself
- USB debugging enabled in settings
- Python

The database file contains all messages and metadata. This is the most important one. But when you look in your Android files you will notice this file is encrypted. Therefore we will need to have the encryption key. This makes it possible to decrypt the messages and make a normal database from it. The last file isn't required but proves very usefull. It tells which phone number is from which person. Knowing this tells you more about the identity of the person and can be very important in digital forensics.

# Installation process
First we need to aquire the required files. This can be done in a lot of different ways and many tools have been written to do this. The first option is doing so by rooting your Android phone. The second one is using Google Drive to get the backup files (if you have google drive backup enabled). Another way is using "WhatsApp Key/DB Extractor", this tool can be used whithout rooting your Android phone and is most likely the best option for you.\
After this we will need to decrypt the files or if they are already decrypted, run the tool to generate a HTML page that displays all messages.

## Using Google Drive (Outdated)
First I wanted to try and get my backup files through Google Drive as my Whatsapp makes a backup to it weekly. This sadly didn't pan out because the tool provided for this called "WhatsApp Google Drive Extractor" does not work anymore. Google changed the way they accept API calls and how they do authorization for certain files. After spending a lot of time trying to get this to work I decided to try one of the other options. You can find the tool here https://forum.xda-developers.com/t/tool-whatsapp-google-drive-extractor-updated-october-2016.3483633/ 

## Using a rooted Android Phone (Option failed)
The use of rooting software on our school laptops is being blocked and therefore can not be run but I was able to bypass this by using a Virtual Machine that was running Windows 10. As I had rooted my phone I hoped to find the key encrypted file. This file should become visible whenever you root the device. Sadly enough rooting the device didn't show me the file. It should have been visible in the data/data/com.whatsapp/ folder.

## Non-rooted device using "WhatsApp Key/DB Extractor" (fully working)
This option is most likely one of the more interesting for digital forensics as it does not require to change your Android device. This option requires us to install some extra tools and drivers.
- Java
- ADB (Android Debug Bridge) Drivers
- Android device with Android 4.0 or higher.
- The tool itself (https://www.xup.in/dl,18324514/Whatsapp_Xtract_2.3_2018-04-25.zip/)

You can enable USB debugging in Settings under "Developer Options" --> "USB Debugging" and when connected to the pc accept the prompt which grants USB debugging access to the pc.  

### 1. Installing drivers
We also need extra drivers to work with the tool. This connects the Android Phone to the tool. These drivers have to be manually installed by doing the following.
First download the driver installer by downloading it from the website (https://forum.xda-developers.com/t/official-tool-windows-adb-fastboot-and-drivers-15-seconds-adb-installer-v1-4-3.2588979/) or directly here (https://forum.xda-developers.com/attachment.php?attachmentid=4623157&d=1540039037 for current latest version 1.4.3). When you run the installer answer 'Y' to every question and then you will be prompted with a driver install window. Go through the process and see that the driver is installed correctly.
This driver however seems to have a problem at first. I fixed this by following the tutorial of savadam. https://youtu.be/LbAq6d2Du0U. In short he goes to device manager and reinstals the driver. ![image](https://user-images.githubusercontent.com/55882105/141073088-2ab71947-c68e-470b-9430-674dbf4733af.png)

After doing so the driver will function appropriately.

### 2. Installing JAVA
Make sure you have JAVA installed on your device you can do this by going to there website and downloading the latest version. https://www.java.com/download/ie_manual.jsp 

### 3. Installation and use of the tool
If everything is setup we can go over downloading and installing the tool which will give us are required files. I downloaded the tool from the authors Github Page. https://github.com/AbinashBishoyi/WhatsApp-Key-DB-Extractor-UnOfficial. Download the tool by downloading the whole repository. See in the picture below.\
![image](https://user-images.githubusercontent.com/55882105/141074305-896aa8de-b585-4d2e-ae55-8e0d904d2c57.png)\

Now extract the folder and look for the "WhatsAppKeyExtract.bat". Run the file and a prompt will appear. If it gives an error just click OK and you should be fine.\
![image](https://user-images.githubusercontent.com/55882105/141074894-870b19cb-4dba-4796-b686-ba8416f2ca11.png)\
After this you will have to unlock your phone and click "MAKE-BACKUP" (you can enter a password if you would like).\
If the backup is complete you will see in the prompt that the program ended. Last you can verify that everything ran correctly by checking the "extracted folder". If you can see the files msgstore.db and wa.db. Also there should be a folder with the Whatsapp decryption key.\
![image](https://user-images.githubusercontent.com/55882105/141075500-842b396c-21a9-46a8-96a5-23a695ba4c24.png)\
Link: https://forum.xda-developers.com/t/tool-whatsapp-key-db-extractor-crypt6-12-non-root-updated-october-2016.2770982/ 

## Using the tool
Now that we have the required files the only thing left is generate the HTML whith are messages.
If you have downloaded and unzipped the folder we can go ahead and place our 2 important files namely msgstore.db and wa.db in to the folder. You can replace the ones that are already in here because these are empty. \
If you would run it now you will get an error, saying that the table "chat_list" cannot be found. This happenes because the database layout changed in one of the more recent versions of Whatsapp. To solve this open "whatsapp_xtract.py" in a text or code editor and change all occurences of "chat_list" into "chat". As you can see in the picture below I used Visual Studio Code.\ (Press CTRL + H for the menu and then click replace all).
![image](https://user-images.githubusercontent.com/55882105/141077084-b9c84356-c01a-44ae-8c02-f684b542da6f.png)  

Now you can run the program. It will generate an HTML that will automatically open in your browser whenever it finishes.\
You can see your messages, people and groups here and by using CTRL+F it is easy to search through all of this.
Below a preview of the generated HTML file.
![image](https://user-images.githubusercontent.com/55882105/141079395-6ced9891-00ed-4ab7-91b8-00176f20d1d5.png)


# Credits
Whatsapp Xtract - Fabio Sangiacomo and ztedd
Whatsapp Google Drive Extractor - TripCode
ADB Drivers - Snoop05
WhatsApp Key DB Extractor UnOfficial - AbinashBishoyi

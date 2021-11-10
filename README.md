# What is Andriller?
Andriller is a software utility that has a collection of forensics tools for smartphones. It can crack Lockscreens with Patterns, PINs, or passwords, decode app data from Android databases, decodes and extracts information. The reports generated are in HTML and Excel Formats.
# How do you use it?
You'll download the Andriller from https://andriller.software.informer.com/download/
Essentially, you connect a USB cable to an Android device and use the USB Debug mode in the program. Then you execute Andriller by running the code **$./Andriller.py**

# How to install the Program using Windows
If you chose to run it with Windows, first you install python 3.10.0 from https://www.python.org/downloads/release/python-3100/
Then, use **python Andriller.py** so that the program runs, the data is downloaded, and the data is decoded.
# Using VMWare to get the android Emulator!
There's websites out there that allows you to download the Virtual Machine for Android. I tried to do it and I failed miserably. 
But when you're going through the steps that you find either you 
On this website https://www.howtogeek.com/164570/HOW-TO-INSTALL-ANDROID-IN-VIRTUALBOX/.
You can also go to this website https://itechbrand.com/how-to-install-android-in-virtualbox/.
If you go to the howtogeek website, you'll find how to install the proper .iso file for the Virtual Machine
I'd prefer the itechbrand website because it shows you step by step with pictures
The virtual machine setup should look like this:![image](https://user-images.githubusercontent.com/69910906/141039454-93a3a7fd-90f4-428c-ab04-fa74d211f56f.png)

Once all the steps are solved, you'll have your android Emulator and the display should look like this:
![image](https://user-images.githubusercontent.com/69910906/141038420-f4d31c69-b4b0-4691-bb9b-1acaab075a1e.png)
# How is it Beneficial with Digital Forensics?
We're in a world where cell phones hold a TON of information benefiting the digital forensics field.
Decrypting and Extracting data is a few of the key points in helping find valuable information
With Andriller, you can gain access to call logs, messages, emails, and social media activity.
It'll access a lot of the databases inside of the device allowing you to piick and choose which data you would like to extract.
![image](https://user-images.githubusercontent.com/69910906/141035206-22fcd5ab-5335-444b-8284-1c57313de663.png)
Then once it searches and finds all of the data inside the database of the device, it will print it out in a beautiful format like so.
![image](https://user-images.githubusercontent.com/69910906/141051652-7d16513e-7bfc-4a0c-864d-97787025654a.png)
# Let's talk about one of the features: Cracking the Lockscreen
So as previously stated, Andriller is able to use Gesture hashes to help figure out pattern passcodes!
You can learn more about it by visiting this website here: https://resources.infosecinstitute.com/topic/android-forensics-cracking-the-pattern-lock-protection/
But to decrypt gesture hashes, we have to get into SHA-1 again. Android devices store data in unsalted SHA-1 encrypted data
That data is coded similar to this ![image](https://user-images.githubusercontent.com/69910906/141120460-b4eb58c2-4f6d-4204-9147-a5773f6a37aa.png)
and creates the bytes of data.
The bytes of data is stored inside of a folder in the Android system called gesture.key
You'll use an editor such as winhex to compare bytes from the file with a generated dictionary to recover that pattern scheme.
Finally, you use that dictionary and MySQL or any SQLite browser to find the original pattern by Select * from [nameoftable] where hash=[hashesgohere]
Then that's pretty much all you have to do to get the pattern.
![image](https://user-images.githubusercontent.com/69910906/141132828-c5ffaeca-50e3-4b2b-a593-b3c5faf69c2f.png)


# Credit goes to
https://www.youtube.com/watch?v=lnN5c40mb0g for just showing what you can do with Andriller. Also I have a report generated from that video in here
https://github.com/den4uk/andriller for being the creators and making a Github showcasing Andriller's features and requirements
https://resources.infosecinstitute.com/topic/android-forensics-cracking-the-pattern-lock-protection/ for giving the gesture hash code that helped demonstrate the lock screen passwords!

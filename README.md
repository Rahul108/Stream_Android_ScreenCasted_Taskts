# Introduction
In order to stream tasks (e.g: games, tech-tips etc) from android devices I've choosed `scrcpy` & `OBS Studio`. I'd describe the conf steps here.

## Requirements
* **Distro**: Ubuntu 18.04 LTS
* **Device**: Android (with min 5.0 or above)
## Steps
### 1. Install ADB 
```sh
sudo apt-get install android-tools-adb android-tools-fastboot
```

or you can follow the steps of installing android sdk.
**Install Java**
```sh
sudo apt-get update
sudo apt-get install openjdk-8-jdk
```
**Decalring JAVA_HOME variable in .bashrc**
```sh
export JAVA_HOME="/usr/lib/jvm/java-8-openjdk"
export PATH="$PATH:$JAVA_HOME/bin"
```
**Verify Java Installation**
```sh
java -version
```
**Install Android SDK**

You can download the `Command line tools` from the official site of [Android Studio](https://developer.android.com/studio#downloads). Follow [developers site](https://developer.android.com/studio/command-line/sdkmanager) to know details about the command line tools.

Set path on .bashrc according to where the sdk files were kept
```sh
export ANDROID_HOME="$HOME/Android/Sdk"
export PATH="$PATH:$ANDROID_HOME/tools"
export PATH="$PATH:$ANDROID_HOME/platform-tools"
```
**Confirm ADB installation**
```sh
adb version
```
**Connect Device:**
Connect your android device with USB/Thunderbolt cable on PC, then run
```sh
adb devices
```
`USB Debugging` should be enabled on the android device, otherwise it won't work. 

Btw... after running the command while connecting the device - it should show the device on terminal like this
```sh
➜ adb devices
List of devices attached
93889d84	device
```

### 2. Install Snap
```sh
sudo apt update
sudo apt install snapd
```
`snap` directory should be added on path variables automatically


### 3. Install Scrcpy snap package
```shhttps://github.com/Rahul108/Stream_Android_ScreenCasted_Taskts_On_Ubuntu/blob/master/Files/Android_SC.png
sudo snap install scrcpy=100x20
```
### 4. Start `scrcpy`
```sh
scrcpy
```
Sometimes adb version related issue occurs, on that case, stop the `adb` & `scrcpy.adb` (there's a chance that it may run on background)
```sh
adb kill-server
scrcpy.adb kill-server
```

after running the `scrcpy`, it should show something like this on terminal
```sh
➜ /snap/bin/scrcpy -m 800
INFO: scrcpy 1.16 <https://githu![Screen-Cast of android device with scrcpy](https://github.com/Rahul108/Stream_Android_ScreenCasted_Taskts_On_Ubuntu/blob/master/Files/Android_SC.png)
b.com/Genymobile/scrcpy>
* daemon not running; starting n![Screen-Cast of android device with scrcpy](https://github.com/Rahul108/Stream_Android_ScreenCasted_Taskts_On_Ubuntu/blob/master/Files/Android_SC.png)
ow at tcp:5037
* daemon started successfully
/usr/local/share/scrcpy/scrcpy-server: 1 file pushed. 2.2 MB/s (33622 bytes in 0.015s)
[server] INFO: Device: Xiaomi POCOPHONE F1 (Android 10)
INFO: Renderer: opengl
INFO: OpenGL version: 3.0 Mesa 20.0.8
INFO: Trilinear filtering enabled
INFO: Initial texture: 384x800
```

I've changed the screen size with `-m 800` cause on default screen-cast it shows a little bit distorted.

btw... the casted-screen should show like below (on both rotated views)...

![](https://github.com/Rahul108/Stream_Android_ScreenCasted_Taskts_On_Ubuntu/blob/master/Files/Android_SC.png "=100px")

![](https://github.com/Rahul108/Stream_Android_ScreenCasted_Taskts_On_Ubuntu/blob/master/Files/Android_SC_2.png "=100px")

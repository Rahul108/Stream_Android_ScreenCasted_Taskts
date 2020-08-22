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

### 2. Install Snap
```sh
sudo apt update
sudo apt install snapd
```

### 3. Install Scrcpy snap package
```sh
sudo snap install scrcpy
```

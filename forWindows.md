# Introduction
Tried to configure pc for streaming android tasks. I will capture audio from the android device directly & use laptop's default mic to capture my voice on stream.
# Requirement

## Software
* **Scrcpy**: For casting android device
* **Obs Studio**: For Streaming
* **Sndcpy**: For Capturing audio of android device

## Hardware
* **PC**: With windows 10/8/7
* **Android Device**: Above android 5 


# Steps

## Installing Scrcpy
Go to the official repo of `Scrcpy` & install Scrcpy. There are many methods described there. I've [downloaded the zip](https://github.com/Genymobile/scrcpy/releases/download/v1.16/scrcpy-win64-v1.16.zip) and used `scrcpy.exe`.

### Steps to run `Scrcpy`
**1. First Unzip the file**:

Unzip the file to a specific directory (I have used my `users/{username}/Documents/` directory to install all that stuff)

**2. Open Powershell (with `Run As Administrator`)**: 

Open Powershell & Go to the directory where the files are extracted.
```sh
# Enter into the extracted directory (onto whatever you named that folder)
cd ../../Users/{username}/Documents/scrcpy/scrcpy-win64-v1.16
```

Connect your android device with usb/thunderbolt cable. `Developer options` should be enabled. Enable `Usb Debugging` of the device. 

**3. Check `adb`:**
 
```sh
./adb.exe
```
it will show some output like this:
```sh
Android Debug Bridge version 1.0.41
Version 30.0.4-6686687
Installed as C:\Users\rahul\Documents\scrcpy\scrcpy-win64-v1.16\adb.exe

global options:
 -a         listen on all network interfaces, not just localhost
 -d         use USB device (error if multiple devices connected)
 -e         use TCP/IP device (error if multiple TCP/IP devices available)
 -s SERIAL  use device with given serial (overrides $ANDROID_SERIAL)
 -t ID      use device with given transport id
 -H         name of adb server host [default=localhost]
 -P         port of adb server [default=5037]
 -L SOCKET  listen on given socket for adb server [default=tcp:localhost:5037]
 ... ...

 ... ...
 $ADB_VENDOR_KEYS         colon-separated list of keys (files or directories)
 $ANDROID_SERIAL          serial number to connect to (see -s)
 $ANDROID_LOG_TAGS        tags to be used by logcat (see logcat --help)
 $ADB_LOCAL_TRANSPORT_MAX_PORT max emulator scan port (default 5585, 16 emus)
 $ADB_MDNS_AUTO_CONNECT   comma-separated list of mdns services to allow auto-connect (default adb-tls-connect)
```

**4. Run `scrcpy`:** 

```sh
./scrcpy.ssh
```

Then scrcpy should run and the android screen-casted window should appear

You can also mention your screen size while starting `scrcpy`, like i always use something like this
```sh
./scrcpy.ssh -m 800
```
Cause on default screen size, the display seems to be a little bit distorted while casting.

Btw... there are many more ways to confiure display, check the official doc of [Genymobile/scrcpy](https://github.com/Genymobile/scrcpy/blob/master/README.md) for more info

### Steps to run `Obs Studio`
Follow the [Link](https://obsproject.com/) to download obs studio & install it.

Then run `Obs Studio` from the desktop shortcut

### Steps to run `Sndcpy`

**Installing `Sndcpy`:**

Download the [file](https://github.com/rom1v/sndcpy/releases/download/v1.0/sndcpy-with-adb-windows-v1.0.zip) from the [official repo](https://github.com/rom1v/sndcpy)

**2. Open Powershell (with `Run As Administrator`)**: 

Open the directory of `sndcpy`
```sh
cd ../../Users/rahul/Documents/sndcpy-with-adb-windows-v1.0
```

**3. Copy & install `sndcpy.apk` on the connected android device: **

Install the apk file & give the audio record permission

**4. Run `sndcpy`:**
```sh
./sndcpy.exe
```

It should then capture the android device audio on pc.


# Stream with Obs
## Configure
I've captured the Windows (Screen-casting window) + Audio input (default) + Audio output (Default) .

You can capture things according to your available hardware equipments (like using an external mic)

**Happy Streaming**

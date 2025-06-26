# ![Awesome ADB](./assets/title.png)

**ADB (Android Debug Bridge)** is a powerful and essential tool for Android developers and testers, and a versatile utility for power users of Android devices.

This guide is continuously updated. Feel free to contribute by submitting Pull Requests or Issues.

**Note:** Some commands may behave differently depending on the Android system version and the custom ROM in use.

## 📄 Table of Contents

<!-- vim-markdown-toc GFM -->

* [Basic Usage](#basic-usage)
  * [Command Syntax](#command-syntax)
  * [Targeting a Specific Device](#targeting-a-specific-device)
  * [Start/Stop ADB Server](#startstop-adb-server)
  * [Check ADB Version](#check-adb-version)
  * [Run adbd as Root](#run-adbd-as-root)
  * [Set ADB Server Port](#set-adb-server-port)
* [Device Connection Management](#device-connection-management)
  * [List Connected Devices/Emulators](#list-connected-devicesemulators)
  * [USB Connection](#usb-connection)
  * [Wireless (Android 11+)](#wireless-android-11)
  * [Wireless (via USB)](#wireless-via-usb)
  * [Wireless (No USB)](#wireless-no-usb)
* [Application Management](#application-management)
* [Interacting with Apps](#interacting-with-apps)
* [File Management](#file-management)
* [Simulating Input](#simulating-input)
* [Log Viewing](#log-viewing)
* [Device Information](#device-information)
* [System Settings Modification](#system-settings-modification)
* [Useful Utilities](#useful-utilities)
* [Flashing & Recovery](#flashing--recovery)
* [Security-Related Commands](#security-related-commands)
* [Advanced Shell Commands](#advanced-shell-commands)
* [Common Issues](#common-issues)
* [Unofficial ADB Implementations](#unofficial-adb-implementations)
* [Related Commands](#related-commands)

<!-- vim-markdown-toc -->

## Basic Usage

### Command Syntax

```sh
adb [-d | -e | -s <serialNumber>] <command>
````

If only one device/emulator is connected, you can omit the device selector.

### Targeting a Specific Device

| Flag                | Description                                           |
| ------------------- | ----------------------------------------------------- |
| `-d`                | Target the only USB-connected device                  |
| `-e`                | Target the only emulator                              |
| `-s <serialNumber>` | Target a specific device or emulator by serial number |

You can get the list of serial numbers by:

```sh
adb devices
```

Example:

```sh
adb -s emulator-5554 shell wm size
```

### Start/Stop ADB Server

Start ADB server:

```sh
adb start-server
```

Stop ADB server:

```sh
adb kill-server
```

### Check ADB Version

```sh
adb version
```

Example:

```sh
Android Debug Bridge version 1.0.41
Version 30.0.5-6877874
```

### Run adbd as Root

```sh
adb root
```

To revert:

```sh
adb unroot
```

> ⚠️ Some devices (e.g. Samsung production builds) do not support `adb root`.

### Set ADB Server Port

```sh
adb -P <port> start-server
```

Default is usually 5555. Find the $IP $PORT in Dev Settings or if you have root and termux, set this port to whatever you want. 


Firebird Emu
==========

![Build for Android](https://github.com/nspire-emus/firebird/actions/workflows/android.yml/badge.svg?branch=master) ![Build for macOS](https://github.com/nspire-emus/firebird/actions/workflows/macOS.yml/badge.svg?branch=master) ![Build for Windows](https://github.com/nspire-emus/firebird/actions/workflows/windows.yml/badge.svg?branch=master) [![build result](https://build.opensuse.org/projects/home:Vogtinator:firebird-emu:unstable/packages/firebird-emu/badge.svg?type=percent)](https://build.opensuse.org/package/show/home:Vogtinator:firebird-emu:unstable/firebird-emu)

This project is currently the community TI-Nspire emulator, originally created by Goplat.  
It supports the emulation of Nspire Touchpad (CAS), CX (CAS) and CX II (-T/CAS) calcs on Android, iOS, Linux, macOS and Windows.

Download:
---------

* [Latest release](https://github.com/nspire-emus/firebird/releases/latest)

Screenshots:
-------------------

_Linux:_

[![](http://i.imgur.com/eGJOMsSl.png)](http://i.imgur.com/eGJOMsS.png)

_Windows:_ | _Android:_
--- | ---
[![](https://i.imgur.com/aibTt9Cl.png)](https://i.imgur.com/aibTt9C.png) | [![](https://i.imgur.com/cLphTgnm.png)](https://i.imgur.com/cLphTgn.png)
_macOS:_ | _iOS:_
[![](https://i.imgur.com/ymDtYsj.png)](https://i.imgur.com/O8R2aSo.png) | [![](https://i.imgur.com/LT1u2bim.png)](https://i.imgur.com/LT1u2bi.png)

Building
--------

First, you need to install Qt5.  
Then, you can either use Qt Creator directly (don't forget to configure your kits/compilers etc.!), or run:

```
mkdir -p build
cd build
qmake ..
make
```
##### A special case: iOS with translation (≈JIT) enabled:

There seems to be a bug in qmake that makes the required .S get ignored when building a JIT-enabled ([`TRANSLATION_ENABLED = true`](https://github.com/nspire-emus/firebird/blob/master/firebird.pro#L4)) binary.  
As a workaround, you'll have to take care of it manually:

1. Hit Build in Qt Creator, on an iOS kit/target. (It'll fail)
2. Open the generated .xcodeproj file (in the build folder) in Xcode
3. Locate `asmcode_arm.S` in the file list, click on it, and in the right sidebar, add it to the Firebird target
4. Adjust any other project settings as you see fit (certs/profiles/team/signings/entitlements/etc. though this should be automatic except the Team choice)
5. Build/Run


License
-------
This work (except the icons from the KDE project) is licensed under the GPLv3.

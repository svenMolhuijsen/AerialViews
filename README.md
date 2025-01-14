# Aerial Views

[![API](https://img.shields.io/badge/API-23%2B-brightgreen.svg?style=flat)](https://android-arsenal.com/api?level=23)
[![License](https://img.shields.io/:license-gpl%20v3-brightgreen.svg?style=flat)](https://raw.githubusercontent.com/theothernt/AerialViews/master/LICENSE)

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/I3I86BK6U)

## A screensaver for Android TV devices, including Nvidia Shield, Fire TV, and Google TV. Inspired by the Apple TV's video screensaver

<br/>

This is a forked and modified version which features the following changes...

- Great performance and support for older Android TVs (eg. 2015/ATV1 platform)

- Supports *only* the latest Apple video feed (it contains nearly all previous videos too!)

- Ability to play Apple videos **or any other** stored locally or on a local network (Samba/SMB) share

- HDR support (Dolby Vision is required for Apple's videos)

- Skip video feature (press right on your TV remote's d-pad)

- Alternate text position to help avoid burn-in on OLED TVs

<br/>

## How to install

This version of the app is not available in the Play Store, yet, so your options are...

1. [Download the APK from the Releases page](https://github.com/theothernt/AerialViews/releases) and install it manually

2. Clone this repo to your PC or Mac, download Android Studio, then build and deploy

<br/>

## Where to download Apple videos for offline/local playback

Please [visit this web page to download download the tvOS 15 videos](https://aerial-videos.netlify.app/) supported by this screensaver.

<br/>

## HDR videos don't seem to play, I only see black screen...

Currently, Apple's videos only support Dolby Vision HDR. Even if your TV supports HDR, it might not support Dolby Vision.

Here are some things to try...

* Find the make and model of your TV, search online for a product page for that device and it should list the supported HDR modes (there are several!)

* If you use a Nvidia Shield, please [follow their instructions on how to enable (or confirm) that Dolby Vision playback is possible](https://www.nvidia.com/en-us/shield/support/shield-tv/enable-dolby-vision-hdr10-on-shield/)

* Confirm that Dolby Vision playback works in other apps like Netflix, Disney+, Amazon Prime Video.

<br/>

## Special note for Fire TV owners

The app can be installed and configured, like with any other Android TV device, but the ability to set Aerial Views as the default screensaver has been disabled in the FireOS menus.

To get around this, you'll have to install a command-line developer tool, run a command - and that's it. I would recommend having a look at [this guide over at Nerds Chalk](https://nerdschalk.com/change-fire-tv-screensaver-apple-tv/) for the exact steps.

Just note that the commands are little different due to a name change in the code, try this instead:

`adb shell settings put secure screensaver_components com.amazon.ftv.screensaver/.app.services.ScreensaverService:com.neilturner.aerialviews/.ui.screensaver.DreamActivity` 

`adb shell settings put secure screensaver_default_component com.neilturner.aerialviews/.ui.screensaver.DreamActivity`

<br/>

## How remote and local playback of Apple videos works

- The app contains a video manifest (ie. a list of links) which it uses to figure out what videos to play in which format (1080p, 4K, HDR, etc)

- When using **local** playback, the app searches for the same filenames (eg. xyz.mov) locally instead of making a request to a remote web server

- **Local** videos can be placed in any folder

- When using **local and remote** playback, local videos are used if found, but for missing videos, the remote version is used.

<br/>

## Device support and testing

- The plan is the keep support and great performance for older Android TVs

- Newer features, which require more powerful devices (eg. Nvidia Shield or Google TV) can be disabled or enabled

- The app has been tested with...
  - Sony Bravia (2015, Android v6)
  - Nvidia Shield (2015, Android v7)
  - Fire TV Stick 4K (2018, Android v7)
  - Nvidia Shield (2019, Android v9)
  - Chromecast/Google TV (2020, Android v10)

<br/>

## Known issues

- Sometimes after copying videos to your Android TV device they fail to play or appear during the screensaver. A quick fix is to restart your Android TV device.

- If set to local playback only and there are no videos, there is no error message or notification - only a black screen with the time

- Network connection issues are not handled well, the videos will simply pause

<br />

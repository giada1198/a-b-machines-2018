![header](/img/header_andy.jpg)

# A/B Machines

An immersive theater project that explores people chasing American dream and their self-identity, inspired by Andy Warhol and his philosophy.

## Folder Structure

* **photobooth-controller** - Arduino
* **photobooth-screen** - openFrameworks
* **lip-sync-prototype** - openFrameworks

## Getting Started

### Install openFrameworks

Download the latest version from [Official Website](https://openframeworks.cc/download/) and do not setup any IDE.

### Compile Project using Xcode 10

openFramewroks seems have troubles with being compiled by [Xcode 10](https://forum.openframeworks.cc/t/xcode-10-0-build-errors/30447/6) using default setting and getting access to camera in [macOS 10.4 Mojave](https://www.apple.com/macos/mojave/). You have to modify some settings manually.

#### Environment
* oepnFrameworks 10.0
* Xcode 10.0

In both the project and `openFrameworksLib.xcodeproj`, goto `Build Settings` and show `All` settings, then change **Architectures** to `Standard Architectures (64-bit Intel)` and remove `i386` from **Vaild Architectures**.

Goto `openFrameworks-Info.plist` file to add the privacy key named `NSCameraUsageDescription`.

### Compile without Xcode

Another solution is removing Xcode and only using Command Line Tools to compile and run projects.

Launch the Terminal and type the following command string:

```
xcode-select --install
```

Goto `openFrameworks-Info.plist` file to add the privacy key within `<dict>` below:

```
<key>NSCameraUsageDescription</key>
<string>${PRODUCT_NAME} Camera Usage</string>
```

Use `cd` to the directory of your project and run:

```
make
```

After compiling is done, you can launch the application in `bin` or run:

```
make RunRelease
```

To activate debug mode, run:

```
make Debug
make RunDebug
```

Launch the application, and now you can allow the openFrameworks access to camera:

![camera_access](/img/camera_access.png)


### Install Addons

#### ofxOpenPose

[ofxOpenFace](https://github.com/antimodular/ofxOpenFace/tree/quick) is a toolkit wrapping [OpenFace](https://github.com/TadasBaltrusaitis/OpenFace). It's capable of facial landmark detection, head pose estimation, facial action unit recognition, and eye-gaze estimation.

At first, use [homebrew](https://brew.sh) to install [TBB](https://www.threadingbuildingblocks.org/), openBlas and [openCV](https://opencv.orgGI):

```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"; brew install tbb; brew install opencv; brew install openblas;
```

Goto `/addons/ofxOpenFace/src` replace `return 1;` to `return;`

#### Others
* [ofxCV](https://github.com/kylemcdonald/ofxCv)
* [ofxVideoRecorder](https://github.com/timscaffidi/ofxVideoRecorder)







## Media Design Team
* **Giada Sun** - *Lead Media Design* - [Website](http://giadasun.com)
* **Sean Leo** - *Assistant Media Design* - [Website](https://www.seanbyrumleo.com/)
* **SooA Kim** - *Media Engineer* - [Website](https://www.sooakim.com/)

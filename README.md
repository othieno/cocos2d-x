<img src="http://www.cocos2d-x.org/attachments/801/cocos2dx_portrait.png" width=200>


cocos2d-x
=========

[![Build Status](https://travis-ci.org/cocos2d/cocos2d-x.png?branch=v3)](https://travis-ci.org/cocos2d/cocos2d-x)
[![Build Status](https://travis-ci.org/cocos-travis-mac/cocos2d-x.png?branch=v3)](https://travis-ci.org/cocos-travis-mac/cocos2d-x)

[cocos2d-x][1] is a multi-platform framework for building 2d games, interactive books, demos and other graphical applications.
It is based on [cocos2d-iphone][2], but instead of using Objective-C, it uses C++.
It works on iOS, Android, Windows Phone, OS X, Windows and Linux.

cocos2d-x is:

  * Fast
  * Free
  * Easy to use
  * Community Supported


Main features
-------------
   * Scene management (workflow)
   * Transitions between scenes
   * Sprites and Sprite Sheets
   * Effects: Lens, Ripple, Waves, Liquid, etc.
   * Actions (behaviours):
     * Trasformation Actions: Move, Rotate, Scale, Fade, Tint, etc.
     * Composable actions: Sequence, Spawn, Repeat, Reverse
     * Ease Actions: Exp, Sin, Cubic, Elastic, etc.
     * Misc actions: CallFunc, OrbitCamera, Follow, Tween
   * Basic menus and buttons
   * Integrated with physics engines: [Box2d][5] and [Chipmunk][6]
   * Particle system
   * Skeleton Animations: [Spine][7] and Armature support
   * Fonts:
     * Fast font rendering using Fixed and Variable width fonts
     * Support for .ttf fonts
   * Tile Map support: Orthogonal, Isometric and Hexagonal
   * Parallax scrolling
   * Motion Streak
   * Render To Texture
   * Touch/Accelerometer on mobile devices
   * Touch/Mouse/Keyboard on desktop
   * Sound Engine support (CocosDenshion library) based on OpenAL
   * Integrated Slow motion/Fast forward
   * Fast and compressed textures: PVR compressed and uncompressed textures, ETC1 compressed textures, and more
   * Resolution Independent
   * Language: C++, with Lua and JavaScript bindings
   * Open Source Commercial Friendly(MIT): Compatible with open and closed source projects
   * OpenGL ES 2.0 (mobile) / OpenGL 2.1 (desktop) based


Build Requirements
------------------

* Mac OS X 10.7+, Xcode 5.1+
* or Ubuntu 12.10+, CMake 2.6+
* or Windows 7+, VS 2012+
* Python 2.7.5
* NDK r10c+ is required to build Android games
* Windows Phone/Store 8.0 VS 2012+
* Windows Phone/Store 8.1 VS 2013 Update 3+


Runtime Requirements
--------------------

* iOS 5.0+ for iPhone / iPad games
* Android 2.3+ for Android games
* Windows Phone 8 and 8.1 for Windows Phone games
* OS X v10.6+ for Mac games
* Windows 7+ for Win games
* Windows 8+ for WinRT games (Modern Apps)


Cloning the cocos2d-x repo
--------------------------

The cocos2d-x codebase can be obtained from the [official download site][4] or cloned from this repository.
When cloning the repo, the following steps must be performed:

1. Start by cloning the repository and checking out the most recent version

		$ git clone git@github.com:cocos2d/cocos2d-x.git
		$ cd cocos2d-x
		$ git checkout v3

2. After cloning the repo, please execute the `download-deps.py` script to download and install dependencies

		$ python download-deps.py

3. When the dependencies have been installed, the submodules need to be updated

		$ git submodule update --init


Installing cocos2d-x
--------------------

Before being able to use cocos2d-x, its environment variables need to be added to your system.
The `setup.py` script configures the aforementioned variables and adds them to your .bashrc file

		$ python setup.py
		$ source $HOME/.bashrc

For Linux users, an extra set of dependencies must to be installed before cocos2d-x can be used.
This installation is automated via the `install-deps-linux.sh` script

		$ ./build/install-deps-linux.sh

To make sure the cocos2d-x environment is correctly setup, run the `cocos` script

		$ cocos --version


Creating a new cocos2d-x game
-----------------------------

To create a new project named 'MyGame' in the directory 'MyGameDirectory', run the following

		$ cocos new MyGame -p com.mycompany.mygame -l cpp -d MyGameDirectory

The newly created project can now be built and executed by running

		$ cd MyGameDirectory/MyGame
		$ cocos run -p TARGET_PLATFORM

where TARGET_PLATFORM is your target platform, e.g. ios, android, mac, linux or win32.

For further information about the `new` and `run` commands, please refer to their respective help pages

		$ cocos new --help
		$ cocos run --help

N.B. From cocos2d-x v3.3, you are able to build [universal Windows apps](http://dev.windows.com/en-us/develop/building-universal-windows-apps).
For more info, check out http://msopentech.github.io/cocos2d-x/


Running Tests
-------------

Before running any tests, make sure cocos2d-x is correctly [installed](#installing-cocos2d-x).

Select the test you want from Xcode Scheme chooser.

* For OS X / iOS

```
$ cd cocos2d-x/build
$ open cocos_tests.xcodeproj
```

* For Linux

```
$ cd cocos2d-x/build
$ cmake ..
$ make
```

Run Samples

```
$ bin/cpp-empty-test/cpp-empty-test
or
$ bin/lua-empty-test/lua-empty-test
```

      You may meet building errors when building libGLFW.so. It is because libGL.so directs to an error target,
      you should make it to direct to a correct one. `install-deps-linux.sh` only has to be run once.

* For Windows

Open the `cocos2d-x/build/cocos2d-win32.vc2012.sln`

* For Android

```
$ cd cocos2d-x/build
$ python ./android-build.py cpp-empty-test -p 10
$ adb install ../tests/cpp-empty-tst/proj.android/bin/CppEmptyTest-debug.apk
```

Then click item on Android device to run tests. Available value of `-p` is the API level, cocos2d-x supports from level 10.


Contributing to the Project
--------------------------------

Did you find a bug? Do you have feature request? Do you want to merge a feature?

   * [contributing to cocos2d-x][8]


Contact us
----------

   * Forum: [http://forum.cocos2d-x.org][9]
   * Twitter: [http://www.twitter.com/cocos2dx][10]
   * Weibo: [http://t.sina.com.cn/cocos2dx][11]
   * IRC: [https://webchat.freenode.net/][12] (#cocos2d and #cocos2d-x channels)

[1]: http://www.cocos2d-x.org "cocos2d-x"
[2]: http://www.cocos2d-iphone.org "cocos2d for iPhone"
[3]: http://www.cocos2d-x.org/projects/cocos2d-x/wiki/Download
[4]: http://www.cocos2d-x.org/download/version#Cocos2d-x
[5]: http://www.box2d.org "Box2D"
[6]: http://www.chipmunk-physics.net "Chipmunk2D"
[7]: http://esotericsoftware.com/ "http://esotericsoftware.com/"
[8]: https://github.com/cocos2d/cocos2d-x/blob/v3/docs/CONTRIBUTE.md
[9]: http://forum.cocos2d-x.org "http://forum.cocos2d-x.org"
[10]: http://www.twitter.com/cocos2dx "http://www.twitter.com/cocos2dx"
[11]: http://t.sina.com.cn/cocos2dx "http://t.sina.com.cn/cocos2dx"
[12]: https://webchat.freenode.net/ "https://webchat.freenode.net/"

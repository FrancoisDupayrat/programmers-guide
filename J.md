# Appendix J: (experimental) Android (Gradle & Android Studio) Installation and Setup

## Introduction

Gradle build is not officially supported by cocos2d-x yet, for 2 main reasons:

* Gradle doesn't support NDK build yet

* Android Studio (which is the main reason to switch to Gradle) is still in beta

However, it is fairly easy to build cocos2d-x with Gradle, and even in beta, Android Studio is a great IDE for Android development.

## Prerequisite 

* Complete steps in Appendix B

* `*ANDROID_NDK_HOME`* path must be configured in ~/.gradle/gradle.properties and point to the location of where you put the NDK. (i.e android-ndk-r9d/)

* Add a file `local.properties` in your project `proj.android` folder with a reference to your Android SDK, for example: `sdk.dir=/Users/Fradow/Development/adt-bundle-mac/sdk/`

* Add the following line to your .gitignore

		.gradle/
		**/proj.android/build/**
		.iml		

* Add those files [Gradle Wrapper files](https://github.com/chukong/programmers-guide/blob/master/gradle/wrapper) in your project `proj.android` folder. The Gradle Wrapper will automatically download Gradle for you, and should be checked in your constrol version.

## Create your `build.gradle`

* The build.gradle file describe what's happen during Gradle build. Here is a [build.gradle](https://github.com/chukong/programmers-guide/blob/master/gradle/build.gradle) to get you started.

## How to deploy it on your Android phone via command line

* Enable *[USB Debugging](http://stackoverflow.com/questions/16707137/how-to-find-and-turn-on-usb-debugging-mode-on-nexus-4)* on your phone and then connect your phone via USB.

* Run `./gradlew installDebug` from your `proj.android` to build and run on your phone via USB. (on Windows, use the .bat file instead)

## How to use Android Studio

* Import your `build.gradle` from Android Studio

* Click the Run or Debug button


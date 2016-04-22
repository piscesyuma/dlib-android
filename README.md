# dlib-android

### Purpose
* Port [dlib](http://dlib.net/) to Andriod platform

* You can build it to dynamic or static library for Android. You can also build dlib's sample to Android executable file.

* You can refer to [dlib-android-app](https://github.com/tzutalin/dlib-android-app) which demonstrates dlib-android features

### Grab the source

    $ cd ~
    $ git clone --recursive https://github.com/tzutalin/dlib-android.git

### Prerequisites
* Download Android-NDK from [Android website](https://developer.android.com/ndk/downloads/index.html).

	 After downloading, go to the directory to which you downloaded the package to extract it

	 Export ANDROID_NDK_HOME in ~/.bashrc
     `$ vim ~/.bashrc`

	`export ANDROID_NDK_HOME=[NDK_PATH]/android-ndk-[version]`

    `export PATH=$PATH:$ANDROID_NDK_HOME`

* Install Android Debug Bride (ADB). You can download it via [Android SDK Manager](https://developer.android.com/sdk/installing/index.html) or $ sudo apt-get install android-tools-adb

* [Optional] You can download a specific Android-OpenCV from http://opencv.org/downloads.html.  Download the version and copy the folders in native SDK to dlib-android/third_party/opencv. (Currently, itis 3.1)

* Prepare a Android device for test

### Build and Run
You can change the compiler architecture in dlib-android/jni/Application.mk

Build executable files and shared library, and push the executable files to Android devices. 
```sh
    $ cd [$dlib-android]
    
    Run all test daemons on your arm/x86 devices. Remember to connect to Android device
    $ python build_push.py --test true
    
    Copy the shared lib to your Android project
    $ python build_push.py --android_project dlib-android-app/dlib/src/main/jniLibs/
```
You can build only (Optional)

	`$ ndk-build -j 2`

### Write JNI and build shared library for Android Java application
There are examples in [jnilib_ex](https://github.com/tzutalin/dlib-android/tree/master/jni/jnilib_ex)

There is a sample app to demonstrate the result. [dlib-android-app](https://github.com/tzutalin/dlib-android-app)

### Do you want to contribute
 * If you have any improvement or you've found any bug, send a pull request with the code.

 * Give me a star on this repository
 

### Future task
* Add more examples to [dlib-anroid-app](https://github.com/tzutalin/dlib-android-app)

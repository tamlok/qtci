# QT-CI
This project collects a set of script for building Qt application for Android/iOS in command line environment.

[![Build Status](https://travis-ci.org/benlau/qtci.svg?branch=master)](https://travis-ci.org/benlau/qtci)

Check [.travis.yml](https://github.com/benlau/qtci/blob/master/.travis.yml) to see how it works. 
It will demonstrate how to build a apk file using QT-CI scripts.

Installation
------------

Since this project is a collection of script, and the script in bin folder do not have any dependence to each othter.
It is not necessary to clone / download the whole repository into your build environmnet. 
You may just copy the script you need from this repository. 

Setup
-----

    git clone https://github.com/benlau/qtci.git
    
    source qtci/path.env #Add qtci/bin and qtci/env to $PATH
   

Script
------

**(1) bin/extract-qt-installer**

Extract installer of Qt to target path (for Qt 5.5 or above)

Example:

	extract-qt-installer qt-opensource-linux-x64-android-5.5.1.run ~/Qt

**(2) bin/extract-ifw**

Extract installer of "Qt installer framework" to target path

Example:

	extract-ifw qt-installer-framework-opensource-1.5.0-x64.run ~/QtIfw

**(3) bin/install-android-sdk**

Download and install Android SDK

Example:

	install-android-sdk platform-tool,build-tools-20.0.0,android-19

**(4) bin/build-android-gradle-project**

Build a Qt Android project and sign the APK

Usage:

	build-android-gradle-project pro
	
Required Environment Variables	

	QT_HOME [Required] The home directory of installed Qt. (e.g ~/Qt/5.7)
	KEYSTORE [Optional] The location of keystore. If it is set, it will be used to sign the created apk
	KEYALIAS [Optional] The alias of the keystore
	KEYPASS  [Optional] The password of keystore.


Preconfigured Environment
-------------------------

In the folder "env", it contains a set of script that could download and install specific Qt toolchains for different environment. (Include Android)

Please feel free to modify and submit new environment scripts.

Example

	apt-get install openjdk-8-jdk p7zip

	source path.env #Add $PWD/bin and $PWD/env to $PATH

	#Change to installation path

	qt-5.5.1-android-19 # Install Qt 5.5.1 and Android SDK


Related Projects
----------------

 1. [benlau/quickpromise](https://github.com/benlau/quickpromise) - Promise library for QML
 2. [benlau/quickcross](https://github.com/benlau/quickcross) - QML Cross Platform Utility Library
 3. [benlau/qsyncable](https://github.com/benlau/qsyncable) - Synchronize data between models
 4. [benlau/testable](https://github.com/benlau/testable) - QML Unit Test Utilities
 5. [benlau/quickflux](https://github.com/benlau/quickflux) - Message Dispatcher / Queue for Qt/QML
 6. [benlau/biginteger](https://github.com/benlau/biginteger) - QML BigInteger library

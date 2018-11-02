# Base Android Dockerfile

The purpose of this image is to setup the `ANDROID_HOME` environment variable, download the latest Android SDK command line tools for Linux, and accept all the `sdkmanager` licenses. Other images loading specific platform tools can be based off this image.

Setup was inspired by https://medium.com/@elye.project/intro-to-docker-building-android-app-cb7fb1b97602 and https://azabost.com/dockerizing-android-builds/

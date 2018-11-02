FROM openjdk:8

LABEL maintainer="CJ Davis<cj@cjdavis.me>"
LABEL version="1.0.0"

# Latest version can be found at: https://developer.android.com/studio/#command-tools
ENV SDK_URL https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
ENV ANDROID_HOME /opt/android-sdk

RUN mkdir -p ${ANDROID_HOME} \
  && cd ${ANDROID_HOME} \
  && curl -o sdk.zip $SDK_URL \
  && unzip sdk.zip \
  && rm sdk.zip

ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/tools/bin:${ANDROID_HOME}/platform-tools

RUN yes | sdkmanager --licenses

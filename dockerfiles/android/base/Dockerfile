FROM openjdk:8-alpine

LABEL maintainer="CJ Davis<cj@cjdavis.me>"
LABEL version="1.2.0"

# Latest version can be found at: https://developer.android.com/studio/#command-tools
ENV SDK_URL https://dl.google.com/android/repository/sdk-tools-linux-4333796.zip
ENV ANDROID_HOME /opt/android-sdk
ENV GLIBC_VERSION "2.28-r0"

# Install required dependencies
RUN apk add --no-cache ca-certificates && \
  wget https://alpine-pkgs.sgerrand.com/sgerrand.rsa.pub -O /etc/apk/keys/sgerrand.rsa.pub && \
  wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-${GLIBC_VERSION}.apk -O /tmp/glibc.apk && \
  wget https://github.com/sgerrand/alpine-pkg-glibc/releases/download/${GLIBC_VERSION}/glibc-bin-${GLIBC_VERSION}.apk -O /tmp/glibc-bin.apk && \
  apk add --no-cache /tmp/glibc.apk /tmp/glibc-bin.apk && \
  rm -rf /tmp/* && \
  rm -rf /var/cache/apk/*

RUN mkdir -p ${ANDROID_HOME} \
  && cd ${ANDROID_HOME} \
  && wget $SDK_URL -O sdk.zip \
  && unzip sdk.zip \
  && rm sdk.zip

ENV PATH ${PATH}:${ANDROID_HOME}/tools:${ANDROID_HOME}/tools/bin:${ANDROID_HOME}/platform-tools

RUN yes | sdkmanager --licenses

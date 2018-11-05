FROM crevax/android-sdk:1.1.0

LABEL maintainer="CJ Davis<cj@cjdavis.me>"
LABEL version="1.1.0"

ENV ANDROID_VERSION 27
ENV ANDROID_BUILD_TOOLS_VERSION 27.0.2

## TODO: Learn what this file is for. Produces a warning if it's not found
RUN touch /root/.android/repositories.cfg

RUN sdkmanager "platform-tools" \
  "platforms;android-${ANDROID_VERSION}" \
  "build-tools;${ANDROID_BUILD_TOOLS_VERSION}"

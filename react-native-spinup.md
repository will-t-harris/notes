# Setting up React Native on Linux Mint 20
## [dev.to post](https://dev.to/savagepixie/react-native-setting-up-the-environment-on-linux-mint-3jab)

### Install [JDK](https://openjdk.java.net/)

- `sudo apt install openjdx-8-jdk`

> Note: Make sure that you are using JDK 8 when running your apps, otherwise the build process will fail. So if you update it or have another version alongside it, remember to switch back.

### Install [Android Studio](https://developer.android.com/studio/index.html)

- Download latest version for Linux
- Unpack
- Move to desired location - `/opt` in this case
- Launch by navigating to `/opt/android-studio/bin` and executing `./studio.sh`
- Run through the setup wizard, select custom installation type, make sure to install `Android SDK`, `Android SDK Platform`, `Android Virtual Device`
- symlink to access more easily `ln -s /opt/android-studio/bin/studio.sh android-studio`
- At this point started following https://reactnative.dev/docs/environment-setup
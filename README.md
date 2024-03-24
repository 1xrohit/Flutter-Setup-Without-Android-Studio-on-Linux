# Flutter Setup Without Android Studio on Linux
<a href="https://flutter.dev/">
  <h1 align="center">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://storage.googleapis.com/cms-storage-bucket/6e19fee6b47b36ca613f.png">
      <img alt="Flutter" src="https://storage.googleapis.com/cms-storage-bucket/c823e53b3a1a7b0d36a9.png">
    </picture>
  </h1>
</a>




This repository provides a script to set up Flutter development environment on Linux without using Android Studio. This can be useful if you prefer to manage your Flutter projects without the overhead of Android Studio or if you're facing issues with Android Studio on your system.

## Prerequisites

- Linux operating system (tested on Ubuntu)
- Internet connection

## Steps to Set Up Flutter

Follow these steps to set up Flutter on your Linux system:

### Step 1: Update Package Lists

```bash
sudo apt update
```

### Step 2: Install Dependencies

Install `wget` and `snapd` which are required for downloading files and managing snaps respectively.

```bash
sudo apt install wget -y
sudo apt install -y snapd
```

### Step 3: Install JDK

Install OpenJDK 17 which is required for Flutter development.

```bash
sudo apt install openjdk-17-jdk
```

Verify JDK installation:

```bash
java -version
```

### Step 4: Download and Install Android Command Line Tools

Download the Android Command Line Tools and set up the environment variables.

```bash
ANDROID_SDK_PATH="$HOME/Android"
mkdir -p $ANDROID_SDK_PATH
wget https://github.com/1xrohit/Setup-ReactNative-on-Ubuntu-without-Android-Studio/releases/download/AndroidSDK/Android.zip -O $ANDROID_SDK_PATH/Android.zip
unzip $ANDROID_SDK_PATH/Android.zip -d $ANDROID_SDK_PATH
```

Update PATH in `.bashrc`:

```bash
echo "export ANDROID_HOME=$ANDROID_SDK_PATH/Sdk" >> ~/.bashrc
echo "export PATH=\$PATH:\$ANDROID_HOME/emulator" >> ~/.bashrc
echo "export PATH=\$PATH:\$ANDROID_HOME/platform-tools" >> ~/.bashrc
echo "export PATH=\$PATH:\$ANDROID_HOME/cmdline-tools/latest/bin" >> ~/.bashrc
echo "export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64" >> ~/.bashrc
echo "export PATH=\$PATH:\$JAVA_HOME/bin" >> ~/.bashrc
```

Source `.bashrc` to apply the changes:

```bash
source ~/.bashrc
```

### Step 5: Install Flutter

Install Flutter using Snap package manager and run `flutter doctor` to verify the installation.

```bash
sudo snap install flutter --classic
flutter doctor
```

## Usage

After completing the setup, you can start developing Flutter applications without using Android Studio. You can create new projects, run and debug applications directly from the command line using Flutter CLI tools.

## Social MEDIA LINKS
I hope you've found this guide helpful

Follow me on [Twitter](https://x.com/1xrohit) for more tips.
Happy Fluttering! 🚀

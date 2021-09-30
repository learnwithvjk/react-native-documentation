#### Setup:

Install Android Studio
Install SDK version 21 and 29 (all)
Install SDK tools 29.02 (if possible all)
Install Intel HXAM

add path to .bashrc or .bash_profile 
```
export ANDROID_HOME=$HOME/Android/Sdk
export PATH=$PATH:$ANDROID_HOME/emulator
export PATH=$PATH:$ANDROID_HOME/tools
export PATH=$PATH:$ANDROID_HOME/tools/bin
export PATH=$PATH:$ANDROID_HOME/platform-tools
```

> Install HomeBrew:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> /home/vijay-7898/.bash_profile
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```
Check if Home brew is installed 
``` 
brew help 
```
> Install yarn:
```
sudo apt remove cmdtest
sudo apt remove yarn
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt-get update
sudo apt-get install yarn -y
```

> Install WatchMan:

```
brew install watchman
```

> Init Project:
```
npx react-native init AwesomeProject
```


> Init TypeScript Project:
```
npx react-native init AwesomeTSProject --template react-native-template-typescript
```

#### Setting up Virtual Android Device

> Installing KVM for Android Virtual device performance imporvements:
```
sudo apt-get install cpu-checker
egrep -c '(vmx|svm)' /proc/cpuinfo
```
Check if your device is compatable with KVM:
```
kvm-ok
```
if the output is "INFO: /dev/kvm exists KVM acceleration can be used" then we can use this

Installing KVM:
```
sudo apt-get install qemu-kvm libvirt-daemon-system libvirt-clients bridge-utils
```

Now open Android studio
AVD manager
Create Virtual Device
Select Phone
Select API 29
Give a name
Finish
Run the device

#### Running React native app

Starting Metro (it is a JS Bundle that contains react-native. it returns a singe JS file that includes all our code and dependencies and its similar to webpack)

```
npx react-native start
```

Check if Java is installed and Home directory is set:

Finding the home directory:
```
readlink -f $(which java)
```
Set the JAVA Home directory from the above got value after removing "bin/java" at the end
```
export JAVA_HOME="path_to_java_home"
```

Now open Android studio and open the created project's android folder
Start the App!!


> Below is an alternative (which is not working though)
Starting Android Application requires another terminal and type in the below command
```
npx react-native run-android

```


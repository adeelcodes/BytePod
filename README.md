## BytePod

BytePod is a mobile application that allows users to create, listen and share short audio podcasts with their friends. The application is built using Kotlin Multiplatform (KMP) and will be available for both Android and iOS.

## Getting Started

### Prerequisite
* Mac machine
* [Homebrew](https://brew.sh/)
* Kdoctor
* Ruby 2.7
* Cocoapods
* Android Studio
* KMM plugin
* XCode

A detailed tutorial on the setup can be seen here as well: https://youtu.be/7Wl-G8aXxDA

### Installation

If Brew isn't installed then install it like this

#### Brew
```console
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
#### Kdoctor
Kdoctor can be installed like this

```console
brew install kdoctor
```

#### Ruby 2.7

1. Install rbenv - Ruby version manager
2. Install Ruby 2.7
3. Mark 2.7 as global Ruby version
4. Verify
5. Close the terminal and open again - optional

```console
# 1
brew install rbenv
rbenv init

# 2
rbenv install 2.7

# 3
rbenv global 2.7

# 4

ruby -v
```
Further instructions can be found here: https://antran.app/2021/m1_mac_part2/

NB: If you see that the Ruby version isn't 2.7 then you will probably have to enter env variables in bash/zsh manually like below
```console
nano ~/.zshrc
```
**Paste the following**
```console
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init -)"
export PATH="/Users/[your_user_name]/.rbenv/shims:${PATH}"
```

#### Cocoapods

```console
sudo gem install cocoapods
```

#### Android Studio

https://developer.android.com/studio

#### KMM plugin

After Android studio is installed, proceed to Preferences > Plugins > search for `kotlin multiplatform mobile` install and enable.

#### Xcode

- Available in App Store.
- Download from https://developer.apple.com/xcode/

After installing all the above if you type `kdoctor` in the terminal, you will see that all the dependencies are fulfilled.

### Running the apps

Clone the project from GitHub https://github.com/adeelcodes/BytePod.git

**Android**

Open Android Studio > Open project > Press play on Android app.
If running the Android application fails then ensure that the JDK used is 11+.
The setting can be checked from Android Studio via File > Project Structure > SDK Location > JDK section.

If the JDK version is incorrect then Gradle might fail to resolve all the plugins. It will indicate this with the appropriate error.
If that is the case then set the JDK version as mentioned above.

> Could not resolve com.rickclephas.kmp:kmp-nativecoroutines-gradle-plugin:0.13.2.

If the podInstall task fails then a potential fix is to run **pod repo update** from the command line.

```
Execution failed for task ':shared:podInstall'.
> 'pod install' command failed with code 31.
  Full command: pod install
  Error message:
  Analyzing dependencies
  [!] CocoaPods could not find compatible versions for pod "SwiftLint":
    In snapshot (Podfile.lock):
      SwiftLint (= 0.49.1)
    In Podfile:
      SwiftLint
  None of your spec sources contain a spec satisfying the dependencies: `SwiftLint, SwiftLint (= 0.49.1)`.
  You have either:
   * out-of-date source repos which you can update with `pod repo update` or with `pod install --repo-update`.
   * mistyped the name or version.
   * not added the source repo that hosts the Podspec to your Podfile.
          Please, check that podfile contains following lines in header:
          source 'https://cdn.cocoapods.org'
```

**iOS**

Open Xcode and open iosApp > `iosApp.xcworkspace` file. Press Build and it should run the app.
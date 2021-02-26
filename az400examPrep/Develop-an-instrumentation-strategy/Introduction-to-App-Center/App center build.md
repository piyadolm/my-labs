# How App Center Build works

You can connect App Center Build to the source code of your app, it will take care of the build.
This service eliminate the need of building on developer machines or configuring a build server yourself.

## Connect App Center to source code

Supported platforms:

* iOS
* Android
* UWP
* tvOS

Supported frameworks:

* Swift
* Kotlin
* Xamarin
* Java
* Unity
* React Native

Supported source control systems:

* GitHub
* Bitbucket
* Azure DevOps

## Create a build from app source code

1. Connect App Center to your source code repositories
2. Configure branches to be built

    * Auto build when commit
    * Manually build

3. Configure signing of your build

Additionally, if your build requires special processes, there is also a system for creating custom build scripts that run at various points within the build lifecycle: post-clone, pre-build, and post-build. These scripts can take advantage of environment variables provided either by App Center or your own custom variables.

## How are apps built?

* When App Center builds your app, it is built using a **clean environment** every time.
* After the app is built and the release is saved, the VM used to build your app is discarded.
* Builds for **iOS and Android** apps are run on **macOS VMs**.
* **UWP** apps are built on VMs using Hosted **Windows Agents**.

## Test your app launches on real devices?

In the build configuration, you can toggle setting to test on real devices after built, App Center will **launch your app on a physical device and take a screenshot** of the result.

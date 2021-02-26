# What is App Center?

## What is automated user interface testing?

Executing a set of commands against a running app to ensure that you receive the expected outcomes.

* **App Center Test** is the service in App Center that runs **automated UI testing** on native and hybrid mobile apps.
* These tests run against **physical devices in a Microsoft data center**
* Allow you to review
    - The resulting success status
    - Logged information
    - Captured screenshots

## What is continuous integration (Automate UI testing)?

The practice where source code is frequently run through various processes (**A set of tests**) to ensure it is in a known-working state, **to improve software quality**, specifically by finding issues before they are delivered to the end user.

When configured in App Center, the service will **make sure the app builds** and can also **execute repeatable automated user interface tests** against real mobile devices.

## What is continuous delivery (Real testers & Users)?

The ability to **deploy a new version of your app to your users automatically** when a new build is ready.

Once the new feature is in the correct location in source control, automated system will:

1. Pick up the **latest code**
2. **Build** an app deliverable
3. Make that app available for **testers** (or any number of internal or public app stores)

## What is Visual Studio App Center?

A collection of several common mobile development and cloud integration services.
Service such as:

* Continuous integration
* Continuous delivery
* Automated UI testing

After an app is in use by testers or customers, App Center provides services to **monitor the usage and issues with their apps**, and to reach and engage their users with push notifications.

### App Center work flow

If your development process involves the **build, test, and distribution services**:

1. Developers makes a commit to the desired source control brach
2. App Center build the app for iOS and Android
3. App Center run integrated UI test
4. App Center deploy app to App Stores (App App Store, Google Play Store)

### When your app uses the analytics and diagnostics services

App Center can start **collecting analytics** and **diagnostic data** from the app as soon as your **testers and customers begin using the app**.

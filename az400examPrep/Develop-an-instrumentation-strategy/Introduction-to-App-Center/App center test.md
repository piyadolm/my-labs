# How App Center Test works

App Center can run test suites against your app's user interface (UI). **These tests will be performed on your app while it is running on physical devices.**

## What is a device configuration?

The device configuration is the combination of device model and operating system version.

## What is a device tier?

Device Tier | Description | Volumes | Wait time when running tests
-------------- | ----------------- | ----------------- | -----------------
 1 | Flagship phones | Large | Shorter
 2 | Tier 1 devices that older | |
 3 | Edge devices that are not common or popular | Smaller | Longer

## What is a device set?

A collection of device configurations. These collections provide convenient access to devices that are commonly used for repeated tasks.

## What devices are available?

[list of available devices and their operating system version](https://docs.microsoft.com/en-us/appcenter/test-cloud/devices/android)

* You will find the most common device configurations, representing the most popular devices from major manufacturers.
* You can also find older configurations of popular devices that may have reached the end of their system updates.

## What is a test run?

An execution of a **set of tests against a device set** using an application binary.

## Execute a test run on physical devices

1. Start testing devices (**device set**)
2. The application and test files are loaded.
3. Tests are run on the device.
4. **App Center Test** will maintain any **logs or screenshots** that are generated during the run in the resulting test report. These **reports are maintained for 6 months**.

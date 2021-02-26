# How App Center Distribute works

You can use App Center Distribute to deliver a release to a target audience.

If you have pre-release testers, you can distribute the latest alpha or beta release to them in order to gather their feedback.

You can also distribute your release builds to a public app store.

## What is a distribution group?

A collection of users that you can manage together.

These groups allow you to **configure access to releases for everyone** in a distribution group at once.

Distribution groups can be private or public, with private being the default.

### Private Distribution Group

* **Testers who are invited via email** are able to access the releases that are available to the group
* Tester will receive new release notification emails
* Must **sign in to their App Center Account** to access releases

### Public Distribution Group

* Allows for **unauthenticated installs from public links**.
* After a group is named, it can be made public.
* Members will receive notification emails about new releases. Additionally, a public download link that will **not require signing** in to download the release.

Example:

Internal test:

* A **private** group of internal **alpha** and **beta** testers
* A **private** group of internal **QA** users

External test:

* A **private** group of external **beta** testers
* A **public** group of external **prerelease** users

## What is a shared distribution group

A distribution group that is **used across multiple apps** within a **single organization**.

Shared distribution groups can be either **private** or **public**.

## Add users to distribution groups

1. **Using Email:** New users can be added to distribution groups by email address.
2. **Using AAD:** Users can also be added from Azure Active Directory (AAD) groups.

## Manage iOS devices automatically

With App Center distribution groups, you may want to have these device IDs managed for you. You register your Apple ID credentials and a production certificate, and App Center will manage these device IDs for your. With each release, all devices in a target distribution group will be registered and provisioned. With the devices provisioned, it can re-sign your app to install on any of those distribution group devices.

## Release a build to a distribution group

Once you have a build, whether built by App Center or in your own build system, you'll want to release it to a group for testing. Releases can be done using a few approaches.

Creating can be done from the **App Center build configuration** 

1. Providing the appropriate code-signing certificates
2. Configuration values to App Center.
3. Enable distribution to one or more distribution groups or app stores.

If you create your signed builds from your own build system

1. Upload them to App Center yourself. Uploading builds can be done from the New release button found within the Distribute > Releases section in an App Center app. You can also upload releases using the App Center command-line interface or App Center API.

When your distribution group users start downloading the release, **App Center will count how many installs and unique installs are completed.** This data is available from the Releases data for each release.

## Release a build to an app store

The new releases you upload can also be distributed to app stores or company distribution portals.

For **iOS and Android apps**, you can distribute your app to the Apple App Store, the Google Play Store, and via company distribution through **Microsoft Intune**.

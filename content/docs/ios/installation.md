---
title: "Installation"
description: "This section describes how to implement the Amparo ID iOS SDK in your app."
summary: ""
date: 2025-03-07T10:00:00-03:00
lastmod: 2025-03-07T10:00:00-03:00
draft: false
weight: 810 # use it to order the sidebar
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---

Before usingse the Amparo SDK in your project, follow the next steps:

## Add the dependencies

The AmparoID SDK requires some Swift Packages as dependencies. Please take note of the versions of the packages to ensure full compatibility.

### Package.swift File

If you use a Package.swift file to manage your SPM dependencies, then you just need to add this to the dependencies section in your `Package.swift` file.

```json
.package(url: "https://github.com/airbnb/lottie-spm.git", .upToNextMajor(from: "4.5.1")),
.package(url: "https://github.com/devicekit/DeviceKit.git", .upToNextMajor(from: "5.5.0")),
.package(url: "https://github.com/romanmazeev/MRZScanner.git", .upToNextMinor(from: "1.0.0")),
.package(url: "https://github.com/Alamofire/Alamofire.git", .upToNextMajor(from: "5.10.2")),
.package(url: "https://github.com/lucaszischka/BottomSheet", .upToNextMajor(from: "3.1.1")),
.package(name: "KeychainAccess", url: "https://github.com/kishikawakatsumi/KeychainAccess", .branch("master")),
.package(name: "MRZParser", url: "https://github.com/romanmazeev/MRZParser", .branch("master")),
.package(name: "NFCPassportReader", url: "https://github.com/nfc-id/NFCPassportReader", .branch("main")),
.package(url: "https://github.com/lorenzofiamingo/swiftui-cached-async-image", .upToNextMajor(from: "2.1.1")),
.package(url: "https://github.com/datatheorem/TrustKit", .upToNextMajor(from: "3.0.5")),
.package(url: "https://github.com/aws-amplify/amplify-ui-swift-liveness", .upToNextMajor(from: "1.3.3"))
```


### Xcode Manage SPM
If your project is using Xcode to manage the SPM, then you need to add each package manually.

For this you need to go to your project -> Package Dependencies and add:

| Name | URL | Dependency Rule |
| -------- | ------- |------- |
| Alamofire | https://github.com/Alamofire/Alamofire.git | .upToNextMajor(from: "5.10.2")|
| AmplifyUILiveness | https://github.com/aws-amplify/amplify-ui-swift-liveness | .upToNextMajor(from: "1.3.3")|
| BottomSheet | https://github.com/lucaszischka/BottomSheet | .upToNextMajor(from: "3.1.1")|
| DeviceKit |https://github.com/devicekit/DeviceKit.git | .upToNextMajor(from: "5.5.0")|
| "KeychainAccess" | https://github.com/kishikawakatsumi/KeychainAccess | .branch("master")|
| Lottie | https://github.com/airbnb/lottie-spm.git | .upToNextMajor(from: "4.5.1")|
| "MRZParser" | https://github.com/romanmazeev/MRZParser | .exact("1.1.4")|
| MRZ Scanner |https://github.com/romanmazeev/MRZScanner.git | .exact("1.0.0")|
| NFCPassportReader | https://github.com/nfc-id/NFCPassportReader | .branch("main")|
| swiftui-cached-async-image | https://github.com/lorenzofiamingo/swiftui-cached-async-image | .upToNextMajor(from: "2.1.1")|
| TrustKit | https://github.com/datatheorem/TrustKit | .upToNextMajor(from: "3.0.5")|

In the end, your packages should look like this:
<img src="packages.png" height="auto" alt="Xcode Package Dependencies" />

## Add the xcFramework
Once the dependencies are correctly added you can copy the xcFramework to the project by dragging the file into Xcode.
After copying the file, go to your target -> General and scroll down to Frameworks, Libraries, and Embedded Content and change the xcFramework from 'Do Not Embed' to 'Embed & Sign'.
<img src="embed.png" height="auto" alt="xcPackage Embed & Sign image" />

## Xcode pList and Other Configurations

AmparoID identification process uses multiple device functionalities that requires special access, for this, you need to add some values to your `Info.plist` file and Capabilities.

### NFC access

You need to add this to your `Info.plist` file:

```xml
<key>com.apple.developer.nfc.readersession.iso7816.select-identifiers</key>
	<array>
		<string>A0000002471001</string>
		<string>A0000002472001</string>
		<string>00000000000000</string>
	</array>
```
And in your target's Signing & Capabilities, select "All" and press 
the `+ Capability` button, then select `Near Field Communication Tag Reading`. 

<img src="nfccapability.png" height="auto" alt="NFC Capability image" />

### Camera access
```xml
<key>NSCameraUsageDescription</key>
<string>Esta aplicación usa la cámara para leer tu documento de identidad</string>
```

---
title: "Configuration"
description: ""
summary: ""
date: 2026-08-12T12:59:38-04:00
lastmod: 2026-08-12T12:59:38-04:00
draft: false
weight: 50
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---
### MTLS Configuration
If your app needs to secure communication with our servers, you need to create a network-security-config XML file or add our server to your existing configuration.

For the pin-set, contact our team to obtain the correct values for your environment.

### NFC Configuration

By default, our SDK requires your application to support NFC. If you need to remove this requirement, modify your Android manifest and add:

``` xml
<uses-feature
        android:name="android.hardware.nfc"
        android:required="false"
        tools:replace="android:required" />
```

This will override the SDK’s default declaration.

**Note:** By making NFC optional, your application can be installed on devices that do not support NFC. However, our SDK will not work on those devices.
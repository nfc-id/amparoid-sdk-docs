---
title: "Usage"
description: "This section describes how to use the Amparo ID Android SDK."
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 40
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---
### Register Activity Request for Result

Before initializing the SDK, an activity must be defined to receive the result:
```
private val amparoLauncher = registerForActivityResult(ActivityResultContracts.StartActivityForResult()) { result ->
    if (result.resultCode == Activity.RESULT_OK) {
        val sdkResult = result.data?.getStringExtra("SDK_RESULT")
        Toast.makeText(this, "SDK Result: $sdkResult", Toast.LENGTH_LONG).show()
        // Manejar éxito
    } else {
        Toast.makeText(this, "SDK Cancelled or Failed", Toast.LENGTH_LONG).show()
        // Manejar error o cancelación
    }
}
```

### Creating SDK Configuration

The following parameters are required for SDK configuration:
- `API_KEY`: key for API endpoint consumption.
- `API_URL`: API base url.
- `CONTACT_CALLBACK_URL`: contact URL for the SDK help buttons.
- `E_CERT`: security certificate used by the SDK.
- `KSM_KEY`: SDK security key.
- `SKM_KEY`: SDK security key.

To use the Amparo ID SDK, create a configuration using the `AmparoIdSdkConfig` object as shown
below:

```
val amparoIdSdkConfig = AmparoIdSdkConfig.Builder()
    .setApiKey("API_KEY")
    .setBaseUrl("API_URL")
    .setContactCallbackUrl("CONTACT_CALLBACK_URL")
    .setECert("E_CERT")
    .setKsmKey("KSM_KEY")
    .setSkmKey("SKM_KEY")
    .build()
```

This instance will be used when invoking the SDK.

### Initializing the SDK

Obtain an instance of `AmparoIdApi`:
```
amparoIdSdk = AmparoIdApiFactory.create()
```
Call the SDK using the defined `launcher`:
```
amparoIdSdk!!.startActivityForResult(this@MainActivity, amparoIdSdkConfig, amparoLauncher)
```



### SDK Customization

#### Defining colors

#### Defining texts



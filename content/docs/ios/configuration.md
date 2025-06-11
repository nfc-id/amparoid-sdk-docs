---
title: "Configuration"
description: "This section describes how to configure the Amparo ID iOS SDK in your app."
summary: ""
date: 2025-03-07T10:00:00-03:00
lastmod: 2025-03-07T10:00:00-03:00
draft: false
weight: 820 # use it to order the sidebar
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---

With the objective of creating a simple way to configure AmparoID in your app we created the `AmparoIdConfig` class. In the configuration we assume we have access to the strings listed in the [Requirements section](../requirements) 

## Create the configuration

The creation of the configuration requiere the strings given to you to access the AmparoID services.  And add the `resultCallback`.

The `resultCallback`is a function that gets as a parameter an AmparoResult an enum with the cases `completed` or `interrupted`. This indicates if the identification flow was completed or was interrupted due some error or problem from the user.

The creation of the configuration should look something like this:

``` swift
let config = AmparoIdConfig(
        sdkApiKey: API_KEY,
        baseUrl: API_URL,
        ksmKey: KSM_KEY,
        skmKey: SKM_KEY,
        eCert: E_CERT, 
        resultCallback: {result in
                print("The response is : \(result)")
        })
````

## Optional configurations

### Main Color

The main color option allows you to change the color of the identification process interface, to use the color that suits your brand. It receive a `Color`.

```swift
    config.mainColor = Color(red: 1, green: 0, blue: 0)
```

### Default Country

The default country option allows you to change the default image for the identity card in the identification process. By default is `CHL`. For now is compatible with `CHL` and `URY`. It receive a `String` in the 3 letter ISO country code .

```swift
    config.defaultCountry = "URY"
```

### Help Message Time
During the identification process if the user stays in one step for more than 30 seconds a message appears to suggest to contact support if they has problems. The time for the message can be adjusted by the `helpMessageTime` value. It receive an int in seconds.
```swift
    config.helpMessageTime = 45
```

### Contact Button
In some part of the identification process the user is prompted to contact support to get help when they encounter an error or problem. You can set text and action of this button with this configuration.

As a helper, if you use Whatsapp as a contact method you can use our WhatsApp function to open the app as part of the action.

The configuration is with `contactButtonText` that defines a string as the text in the contact support button, and `contactSupport` that receives a function to call when the support button is pressed.

```swift
    config.contactButtonText = "Contact support"
    config.contactSupport = {
        print("Contacting support")
        WhatsappConn.openChatWith(phoneNumber: "+56900000000")
    }
```
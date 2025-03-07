---
title: "Use of the SDK"
description: "This section describes the requirements to implement the Amparo ID iOS SDK in your app."
summary: ""
date: 2025-03-07T10:00:00-03:00
lastmod: 2025-03-07T10:00:00-03:00
draft: false
weight: 850
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---

## Initialize the SDK

For the proper functioning of the AmparoID SDK we need to initialize some assets, for this, we created the function `amparoinit()`. The recommendation is to call this function at the start of the app, in the init function, as shown in the following example:

```swift
@main
struct demoApp: App {
    init () {
        AmparoId.amaparoInit()
    }
    var body: some Scene {
        WindowGroup {
            ContentView()
        }
    }
}
```

## Set the configuration
Following the instructions in the [Configuration section](../configuration), we have the `AmparoIdConfig` object, and now we have to add the configuration to the SDK. We can do this with the `setConfig` function:

```swift
AmparoId.setConfig(config: config)
```

You can create a function to create and set the configuration as follows:

```swift
func amparoSetup() {
    let config = AmparoIdConfig(
        sdkApiKey: API_KEY,
        baseUrl: API_URL,
        ksmKey: KSM_KEY,
        skmKey: SKM_KEY,
        eCert: E_CERT, 
        resultCallback: {result in
                print("The response is : \(result)")
        })
    config.mainColor = Color(red: 1, green: 0, blue: 0)
    config.contactButtonText = "Contact support"
    config.contactSupport = {
        print("Contacting support")
        WhatsappConn.openChatWith(phoneNumber: "+56900000000")
    }
    AmparoId.setConfig(config: config)
}
```

## Start an Identification flow

The identification process is wrapped in the `AmparoWrapper` view. This struct has two parameters, an `Int` called `step` and a `Binding<[Int]>` called path, used to control the NavigationStack, this is necessary to manage navigation and return to the original view at the end of the identification process.

```swift
struct ContentView: View {
    
    let a: () = amparoSetup()
    @State private var path: [Int] = []
   
    var body: some View {
        NavigationStack (path: $path) {
            VStack {
                               
                Button("Identificar") {
                    path.append(1)
                }
                .foregroundColor(.white)
                    .padding()
                    .background(Color.blue)
                    .cornerRadius(10)
            }
            .padding()
            .navigationDestination(for: Int.self) { value in)
                AmparoWrapper(step: value, path: $path)
            }
        }   
    }
}
```
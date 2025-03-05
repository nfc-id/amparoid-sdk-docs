---
title: "Installation"
description: "This section describes how to install the Amparo ID Android SDK in your app."
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 30
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---

To use the Amparo SDK in your project, follow these steps:

1. __Add the repository to the `build.gradle` file__.

First, you need to add the private repository to your `build.gradle` file.
This repository requires authentication, so you will need to provide your GitHub credentials.

```
repositories {
    maven {
        url = uri("https://maven.pkg.github.com/nfc-id/amparoId-Android-SDK")
        credentials {
            username = System.getenv("GITHUB_USER")
            password = System.getenv("GITHUB_TOKEN")
        }
    }
    google()
    mavenCentral()
}
```

2. __Add the dependency to the `build.gradle` file__.

Next, add the Amparo SDK as a dependency in your `build.gradle` file.

```
dependencies {
    implementation("cl.amparo.id:amparo-sdk:1.0.0")
}
```

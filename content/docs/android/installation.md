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

To use the Amparo SDK in your project, follow the next steps:

## Generate a GitHub token

To access the private repository, you will need to generate a GitHub token with
`read:packages` permissions (see [About permissions for GitHub Packages](https://docs.github.com/en/packages/learn-github-packages/about-permissions-for-github-packages)).

## Add the repository to the `build.gradle` file

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
    maven {
        setUrl("https://jitpack.io")
    }
}
```

## Gradle configuration

In general, the Amparo ID SDK for Android requires the following configurations:

- minSdk = 28
- targetSdk = 34
- jvmTarget = "1.8"

Additionally, since the SDK uses Jetpack Compose, it must be enabled by adding the following to the android section of the build.gradle file:

```
compileOptions {
    // Support for Java 8 features
    coreLibraryDesugaringEnabled true
    sourceCompatibility JavaVersion.VERSION_1_8
    targetCompatibility JavaVersion.VERSION_1_8
}
buildFeatures {
    compose true
}
composeOptions {
  kotlinCompilerExtensionVersion '1.2.0'
}
```

The SDK also requires the following dependencies:

```
dependencies {
    implementation("cl.amparo.id:amparo-sdk:1.0.0")
    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:1.1.5")
}
```

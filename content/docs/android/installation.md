---
title: "Installation"
description: "This section describes how to install the Amparo ID Android SDK in your app."
summary: ""
date: 2023-09-07T16:04:48+02:00
lastmod: 2023-09-07T16:04:48+02:00
draft: false
weight: 810
toc: true
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  robots: "" # custom robot tags (optional)
---

### SDK installation

The `aar` file provided by Amparo ID can be added as a project dependency by following the official
Android documentation on [Add your AAR or JAR as a dependency](https://developer.android.com/studio/projects/android-library#psd-add-aar-jar-dependency).

Steps to follow:
1. Create a directory within the project to store the `aar` file.
2. Move the `aar` file to the created directory.
3. Add the dependency to `build.gradle`:
```
dependencies {
    implementation(files("path_to_aar/amparoIdSdk.aar"))
}
```
Where `path_to_aar/amparoIdSdk.aar` should be replaced with the actual file path.
4. Synchronize the project with Gradle files.

### Application configuration
In general, the Amparo ID SDK for Android requires the following configurations:
- `minSdk = 28`
- `targetSdk = 34`
- `jvmTarget = "1.8"`

Additionally, since the SDK uses `Jetpack Compose`, it must be enabled by adding the following to
the `android` section of the `build.gradle` file:

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

### Dependencies installation

Also, add the following dependencies to your project:

```
dependencies {
    implementation("androidx.core:core-ktx:1.13.1")
    implementation("org.jetbrains.kotlin:kotlin-stdlib:2.0.0")
    implementation("androidx.lifecycle:lifecycle-runtime-ktx:2.8.1")
    implementation("androidx.activity:activity-compose:1.9.0")
    implementation(platform("androidx.compose:compose-bom:2023.08.00"))
    implementation("androidx.compose.ui:ui")
    implementation("androidx.compose.ui:ui-graphics")
    implementation("androidx.compose.ui:ui-tooling-preview")
    implementation("androidx.compose.material3:material3:1.3.0")
    implementation("androidx.camera:camera-core:1.3.4")
    implementation("androidx.camera:camera-camera2:1.3.4")
    implementation("androidx.camera:camera-lifecycle:1.3.4")
    implementation("androidx.camera:camera-view:1.3.4")
    implementation("com.google.mlkit:text-recognition:16.0.0")
    implementation("com.amplifyframework:aws-auth-cognito:1.29.0")
    implementation("com.amplifyframework:aws-predictions:1.29.0")
    implementation("com.amplifyframework.ui:liveness:1.2.6")
    coreLibraryDesugaring("com.android.tools:desugar_jdk_libs:1.1.5")
    implementation("com.github.ByteAmaze:RNCryptor-Android:1.0")
    implementation("com.datatheorem.android.trustkit:trustkit:1.1.3")
    implementation("org.bouncycastle:bcpkix-jdk15on:1.65")
    implementation("com.scottyab:rootbeer-lib:0.1.1")
    implementation("com.squareup.okhttp3:okhttp:4.12.0")
    implementation("commons-io:commons-io:2.11.0")
    implementation("org.opencv:opencv:4.9.0")
    implementation("com.airbnb.android:lottie:6.4.1")
    implementation("com.airbnb.android:lottie-compose:6.4.1")
    implementation("com.jaredrummler:android-device-names:2.1.1")
    implementation("com.github.mhshams:jnbis:1.1.0")
}
```

<!--
## Further reading

- Read [about how-to guides](https://diataxis.fr/how-to-guides/) in the Diátaxis framework
-->

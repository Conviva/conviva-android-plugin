# conviva-android-plugin
Use Conviva Android Plugin for the Byte Code Instrumentation.

## Supported Android Gradle Plugin Versions

Android Gradle Plugin Version >= 7.2 \
Android Gradle Plugin Version < 7.0

#### Note : Conviva Gradle Plugin do not support for the Android Gradle Plugin versions >= 7.0 and < 7.2

## Plugin Integration
The following example shows how to include the plugin:

**Groovy(build.gradle)**

```
// in the root or project-level build.gradle
dependencies {
  ...
// Unified Conviva Plugin supported from 0.3.5 onwards, use
classpath 'com.conviva.sdk:android-plugin:0.3.x'
  ...
}

// in the app, build.gradle at the end of plugins add the
...
apply plugin: 'com.conviva.sdk.android-plugin'
```

**Kotlin(build.gradle.kts)**
```
// in the app, build.gradle.kts at the end of plugins add the
plugins {
    id 'com.conviva.sdk.android-plugin' version 'x.x.x'
}

```

<details>
  <summary><b> Deprecated instructions for including Conviva Plugin <= 0.3.4 based on Android Gradle Plugin versions 7.2 and above or below </b></summary>

## Deprecated instructions for including Conviva Plugin <= 0.3.4 based on Android Gradle Plugin versions 7.2 and above or below

The following example shows how to include the plugin:

```
// in the root or project-level build.gradle
dependencies {
  ...
  // For Android Gradle Plugin version 7.2 and above, use
classpath 'com.conviva.sdk:android-plugin:0.3.x'

// For Android Gradle Plugin version below 7.0, use
classpath 'com.conviva.sdk:android-plugin:0.2.x'
  ...
}

// in the app, build.gradle at the end of plugins add the
...
apply plugin: 'com.conviva.sdk.android-plugin'



// in the app, build.gradle.kts at the end of plugins add the
plugins {
    id 'com.conviva.sdk.android-plugin'
}
```
</details>

## Feature Support and Dependencies

| Features                         | Conviva Sensor Version | Conviva Plugin Version |
|---------------------------------------|-------------------------------|--------------------------|
| **User Clicks detection**              | [>= 0.7.1](https://github.com/Conviva/conviva-android-appanalytics/releases/tag/v0.7.1)                       | [>= 0.2.3](https://github.com/Conviva/conviva-android-plugin/releases/tag/v0.2.3)                |
| **Network Request detection**          | [>= 0.7.3](https://github.com/Conviva/conviva-android-appanalytics/releases/tag/v0.7.3)                       | [>= 0.2.3](https://github.com/Conviva/conviva-android-plugin/releases/tag/v0.2.3)                 |
| **Fragment auto detection** | [>= 0.9.4](https://github.com/Conviva/conviva-android-appanalytics/releases/tag/v0.9.4)                       | [>= 0.3.5](https://github.com/Conviva/conviva-android-plugin/releases/tag/v0.3.5)               |
| **Compose navigation auto detection** | [>= 0.9.4](https://github.com/Conviva/conviva-android-appanalytics/releases/tag/v0.9.4)                       | [>= 0.3.5](https://github.com/Conviva/conviva-android-plugin/releases/tag/v0.3.5)  |
| **Compose click auto detection** | [>= 0.9.4](https://github.com/Conviva/conviva-android-appanalytics/releases/tag/v0.9.4)                       | [>= 0.3.5](https://github.com/Conviva/conviva-android-plugin/releases/tag/v0.3.5) |
| **Trace-parent Header Generation and Collection** | [>= 0.9.4](https://github.com/Conviva/conviva-android-appanalytics/releases/tag/v0.9.4)                       | [>= 0.2.3](https://github.com/Conviva/conviva-android-plugin/releases/tag/v0.2.3)


## Exclude Instrumentation for Specific Packages

By default, Conviva excludes the instrumentation of packages for `android`, `androidx`, `kotlin`, `kotlinx`, and `com.conviva`.

The following example shows how to exclude any specific package from instrumentation:

```
// For Android Gradle Plugin version below 7.0
// in the app build.gradle
...
android {   
    ...
    conviva {
        excludePackages = ["com/example/.*",
                           "org/example/.*"]
    }
    ...
}

// For Android Gradle Plugin version 7.2 and above
// in the app build.gradle
...
android {   
    ...
    conviva {
        excludePackages = ["com/example/**",
                           "org/example/**"]
    }
    ...
}
```

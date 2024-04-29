# conviva-android-plugin
Use Conviva Android Plugin for the Byte Code Instrumentation.

## Supported Android Gradle Plugin Versions

Android Gradle Plugin Version >= 8.x \
Android Gradle Plugin Version < 8.x

## Collection of the user click events of any clickable views via instrumentation
This feature supports tracking the user click events of views when a View.OnClickListener is set in the application and is supported from 0.7.3 version onwards

The following example shows how to include the plugin:
```
// in the root or project-level build.gradle
dependencies {
  ...
// For Android Gradle Plugin version 8.0 and above, use
classpath 'com.conviva.sdk:android-plugin:0.3.x'

// For Android Gradle Plugin version below 8.0, use
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
    
## Collection of the OkHttp/Retrofit/HTTPSUrlConnection/HTTPUrlConnection NetworkRequest Tracking via instrumentation
This feature supports to track the Network Requests triggerred with in application and third party libraries scope as well supported from 0.7.1 version onwards

The following example shows how to include the plugin:
```
// in the root or project-level build.gradle
dependencies {
  ...
// For Android Gradle Plugin version 8.0 and above, use
classpath 'com.conviva.sdk:android-plugin:0.3.x'

// For Android Gradle Plugin version below 8.0, use
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
## To Exclude the instrumentation of any specific package
By default, Conviva excludes the instrumentation of the packages for android, androidx, kotlin, kotlinx and com.conviva. 

The following example shows how to exclude any specific package from instrumentation:
```
// For Android Gradle Plugin version below 8.0
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

// For Android Gradle Plugin version 8.0 and above
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





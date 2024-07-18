# Changelog

[Android Gradle Plugin](https://developer.android.com/build/releases/gradle-plugin) supports the [Transform](https://developer.android.com/reference/tools/gradle-api/7.2/com/android/build/api/transform/Transform) api from version 7.2 and provided a standard component based instrumentation api from [8.0](https://developer.android.com/build/releases/gradle-plugin-api-updates).  

Conviva has two versions of plugins. Version 0.2.x(0.2.1, 0.2.2...) supports the transform api(below AGP 8.x). Version 0.3.x(0.3.1, 0.3.2...) supports the instrumentation api(AGP 8.x and above).

Currently the plugin instruments the View.OnClickListener.onClick(View v) functions and network related classes URLConnection and the Okhttp library.

# 0.3.5 (19/JUL/2024)
* Supports the instrumentation of Jetpack Compose NavController and Clickable classes to auto detect the compose navigation and clicks
* Instruments the androidx NavigationController class to auto detect the navigation using fragments.
* Supports 8.x and backward compatible with all the Android Gradle Plugin versions.

# (13/MAY/2024)
### 0.2.4
* Enhances the Conviva Android Plugin to instrument the [onNewIntent(Intent intent)](https://developer.android.com/reference/android/app/Activity#onNewIntent(android.content.Intent)) function to get callbacks of intents delivered to the activity already running in the foreground.

# (29/APR/2024)
### 0.3.3 & 0.2.3
* Enhances the *Android Conviva Plugin* to [exclude the packages](https://github.com/Conviva/conviva-android-plugin?tab=readme-ov-file#to-exclude-the-instrumentation-of-any-specific-package) from the *Conviva Instrumentation*. By default, Conviva excludes the instrumentation of the packages for `android`, `androidx`, `kotlin`, `kotlinx` and `com.conviva`.
* Fixes the bytecode instrumentation to the wrapper (Decorator Pattern), instead of making the replacements independent of other instrumentations.


# (15/NOV/2023)
### 0.3.2 & 0.2.2
* Fixes the ArrayIndexOutOfBounds issue when instrumented the View.OnClickListener.onClick() lambda with several arguments in the bytecode.


# (07/SEP/2023)
### 0.3.1
* Fixed the ArrayIndexOutOfBoundsException issue in the visitInvokeDynamic instruction instrumentation

### 0.2.1
* Fixed the commonsuperclass exception due to jetpack compose.


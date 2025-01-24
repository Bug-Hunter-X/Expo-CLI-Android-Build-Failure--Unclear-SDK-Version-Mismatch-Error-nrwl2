# Expo CLI Android Build Failure: SDK Version Mismatch

This repository demonstrates a common yet often difficult-to-diagnose error in Expo CLI: Android build failures due to mismatched Android SDK versions.

The problem manifests as a cryptic error message during the build process, making it hard to pinpoint the root cause. This repository provides a reproduction scenario and a solution.

## Reproduction

1. Clone this repository.
2. Attempt to run the Expo project for Android (`expo start` and run Android).
3. Observe the build failure.  The exact error message will vary depending on the SDK version mismatch, but it will generally point to a build problem without explicitly mentioning the SDK incompatibility.

## Solution

The solution lies in verifying that the Android SDK version defined in the `gradle.properties` file matches the version installed on your system.

1. **Check Installed SDK Version:**  Use the Android SDK Manager (or command-line tools) to see what SDK versions are installed.
2. **Update `gradle.properties`:** Ensure that the `ANDROID_SDK_ROOT` path in `gradle.properties` points to the correct location of your Android SDK and that the SDK version used in the project's dependencies are compatible.
3. **Clean and Rebuild:** After updating `gradle.properties`, clean the project and rebuild.

## Additional Notes

* This issue often arises when switching between different versions of the Android SDK or when working on multiple projects with different SDK requirements.
* Carefully examine the build logs for more clues.  Though often cryptic, subtle hints about the SDK path or version may be present.
* Using a consistent Android SDK version across projects helps prevent this kind of issue.
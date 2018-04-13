# empty-object-destructuring
Bug example on react native Android release build when render method has empty object destructuring braces

## Reproduce
1. Project is created with: react native init
1. Only this line is added to beginning og render method:
```const { } = styles;```
1. These instructions are used to sign the release package: [Generate Signed APK](https://facebook.github.io/react-native/docs/signed-apk-android.html)
1. When launched in emulator or device with react-native run android it works fine (Device: Honor8, Android 7.0)
1. When installed and launched on device the app crash

It was very frustrating to find the problem because it appeared only on release build and there were quite alot changes and the empty braces was something I didn't expect to be the reason. Of course it was garbage line in my code but I think the bug here is that it should behave the same on debug and release environments.

Create the project

```
android create project --target android-23 --name Werewolves --path /home/gpyh/werewolves/app --activity MainActivity --package com.yacinehmito.werewolves --gradle --gradle-version 1.5.0
```

Remove wrapper and use gradle25

Generating a pair

```
keytool --genkeypair --alias gpyh
```

Move ~/.keystore to project directory

Add `signingConfigs` in build.gradle for apk signing

Create android emulated device

```
android create avd -n device -t android-23
```

Start the emulator

```
emulator -avd device -no-boot-anim -port 5554
```

Install the current project with `gradle installDebug`

Run it

```
adb -s emulator-5554 shell am start -a android.intent.action.MAIN -n com.yacinehmito.werewolves/.MainActivity
```

Add `android-command` dependency so I just have to type `gradle runDebug`

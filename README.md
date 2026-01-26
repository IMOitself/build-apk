# build-apk
the ultimate goal of this repository is to strip [tyron12233/CodeAssist](https://github.com/tyron12233/CodeAssist)'s code to be able to just import files in it and directly build an apk
<br><br>
## Build Instructions

### Prerequisites
[Clone](https://github.com/git-guides/git-clone) this repository and run the command below on the cloned directory:
```cmd
curl.exe -L -o gradle-7.0.2-bin.zip https://services.gradle.org/distributions/gradle-7.0.2-bin.zip
curl.exe -L -o jdk-11.0.29+7.zip https://github.com/adoptium/temurin11-binaries/releases/download/jdk-11.0.29%2B7/OpenJDK11U-jdk_x64_windows_hotspot_11.0.29_7.zip

mkdir temp_build\gradle
mkdir temp_build\jdk

tar -xf gradle-7.0.2-bin.zip -C temp_build\gradle
tar -xf jdk-11.0.29+7.zip -C temp_build\jdk
```

### Build the APK
```powershell
$env:JAVA_HOME="$PWD\temp_build\jdk\jdk-11.0.29+7"
& "$PWD\temp_build\gradle\gradle-7.0.2\bin\gradle.bat" assembleDebug
```

### Output
The built APK will be located at:
```
app\build\outputs\apk\debug\app-debug.apk
```

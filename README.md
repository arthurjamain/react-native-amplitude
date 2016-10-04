# react-native-amplitude

Simple React Native wrapper for Amplitude (Android) tracking

## Installation

1. `npm install react-native-amplitude --save`

2. Install Amplitude Android SDK [more info here](https://github.com/amplitude/Amplitude-Android)

3. Update Gradle settings

```gradle
// file: android/settings.gradle
...
include ':RNAmplitude'
project(':RNAmplitude').projectDir = new File(rootProject.projectDir, '../node_modules/react-native-amplitude/android')
```

3. Update Gradle build

```gradle
// file: android/app/build.gradle
...

dependencies {
    ...
    compile project(':RNAmplitude');
}
```

4. Register React Package

Edit android/app/src/main/java/{NAME OF APP}/MainApplication.java and add the
import:

```java
import com.threedot.reactnativeamplitude.ReactNativeAmplitudePackage;
```

and the line

```java
new ReactNativeAmplitudePackage(getApplication())
```

In below location:

```java
...
import com.threedot.reactnativeamplitude.ReactNativeAmplitudePackage;

public class MainApplication extends Application implements ReactApplication {
...
    @Override
    protected List<ReactPackage> getPackages() {
      return Arrays.<ReactPackage>asList(
...
          new ReactNativeAmplitudePackage(getApplication())
...
      );
    }
  };
...
```

## Usage

```javascript

//Require the module
import Amplitude from 'react-native-amplitude';

//Init Mixpanel SDK with your project token
Amplitude.initialize(YOUR_PROJECT_TOKEN);

//Log an event
Amplitude.logEvent('appStart');
```
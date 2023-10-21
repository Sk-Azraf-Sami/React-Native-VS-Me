# React-Native-VS-Me

### Use own device as 'Emulator' via connected Wifi
<br>
<b>1. Create a `local.properties` file in the `android` folder. Then type this line and save it!
   <br> This is the directory of `SDK` </b>
   <br>
   
   ```
   sdk.dir = /home/sami/Android/Sdk
   ```
   <br>
<b>2. Creating a `debug.apk` file </b>
   <br>
   
   ```
   cd android
   ```
   
   ```
   ./gradlew assembleDebug 
   ```
   Now wait for building the apk. If the apk build successfully, you will get `build success` message
   <br>
<b>3. Now copy the apk file to the android device via usb cable from this location of project folder. </b>
   ```
   /home/sami/Documents/testNative/client/android/app/build/outputs/apk/debug
   ```
   Here, `client` is my project folder. <br>
<b>4. Make sure that your computer and android device are connected to the same wifi network</b>
   <br> Then find `IP` address of your cmputer.
   <br> As a `Ubuntu` user, simply type this in the terminal
   ```
   hostname -I
   ```
<b>5. Now install this app the android device.</b>
   <br> Shake the device
   <br> Go to the settings and type the `IP address`

<b>6. Now run this command to the project directory</b>
   ```
   npx react-native start
   ```
<br> 
Video Tutorial: https://youtu.be/ulLllM9WQco?si=TYQR6YgfjqywEgYD

### Using custom font 
1. Download font from google font
2. Then extract zip file and create a `/assets/Font` folder.
   <br> Copy the all font to this folder.
   <br> `link` command is not support to the updated version of react-native because now it supports auto-linking
   <br> Now create a file in the project directory `react-native.config.js`
   <br> Now copy these line in this file
   
```js
   module.exports = {
    project: {
        ios: {},
        android: {}
    },
    assets: ['./assets/Font'],
};
```
Be careful about the font path (assets: ['./assets/Font'])
<br>
3. Now run this command to the project directory. 
```
npx react-native-asset
```
You will get the message of successful link. 
<br>
4. But if you want to see the result, you need to build the app again that means to follow all steps of `Use own device as 'Emulator' via connected Wifi`


### Use Native-Stack component

<b>Error:</b> requireNativeComponent: "RNSScreenStackHeaderConfig" was not found in the UIManager when running android app

<b>Solution:</b> (https://stackoverflow.com/questions/69043806/requirenativecomponent-rnsscreenstackheaderconfig-was-not-found-in-the-uimana)

Solution have in documentation of [reactnavigation doc](https://reactnavigation.org/docs/getting-started)

After install @react-navigation/native you have to install two dependency:
```
npm install react-native-screens react-native-safe-area-context
```
it's mention library.

<b>NB:</b> react-native-screens package requires one additional configuration step to properly work on Android devices. Edit MainActivity.java file which is located in
```
android/app/src/main/java/<your package name>/MainActivity.java.
```
Add the following code to the body of MainActivity class:
```java
@Override
protected void onCreate(Bundle savedInstanceState) {
  super.onCreate(null);
}
```
and make sure to add an import statement at the top of this file:
```java
import android.os.Bundle;
```

   

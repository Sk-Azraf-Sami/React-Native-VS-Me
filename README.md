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
   

   

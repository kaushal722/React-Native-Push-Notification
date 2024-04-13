## React-Native-Push-Notification - React Native App with Push Notifications and Date Picker

This React Native app demonstrates the use of push notifications and a date picker.

**Prerequisites:**

- Node.js and npm (or yarn) installed on your system.
- An Android development environment with Android Studio and the Android SDK installed.
- A Firebase project with Firebase Cloud Messaging (FCM) enabled.

**Installation:**

Install dependencies:

```bash
npm install  # or yarn install
```

**Configuration:**

**Push Notifications:**

1. Follow the setup instructions for the `react-native-push-notification` library ([https://www.npmjs.com/package/react-native-push-notification](https://www.npmjs.com/package/react-native-push-notification)) to integrate push notifications into your React Native project. This typically involves linking the library and configuring your Firebase project details.

2. Implement the library's methods to handle receiving and displaying notifications within your app.

**Date Picker:**

1. Install the `react-native-date-picker` library ([https://github.com/topics/react-native-datepicker](https://github.com/topics/react-native-datepicker)) using npm or yarn:

   ```bash
   npm install react-native-date-picker  # or yarn add react-native-date-picker
   ```

2. Follow the library's documentation for integrating the date picker component into your app's UI and handling user selections.

**Permissions:**

This app requests the following permissions:

- `android.permission.INTERNET`: Potentially used by the push notification library for functionalities like downloading notification content or analytics.
- `android.permission.VIBRATE`: Allows the device to vibrate upon receiving notifications.
- `android.permission.RECEIVE_BOOT_COMPLETED`: Used by the push notification library for initialization purposes on boot completion.
- `android.permission.POST_NOTIFICATIONS` (**New:** Added for sending notifications): Required by the `react-native-push-notification` library to schedule and display notifications within the app.

- `<meta-data android:name="google_analytics_adid_collection_enabled" android:value="false" />
  <meta-data android:name="com.dieam.reactnativepushnotification.notification_channel_name" android:value="NotifcationDemo"/>
  <meta-data android:name="com.dieam.reactnativepushnotification.notification_channel_description" android:value="NotifcationDemo Notifications"/>
  <!-- Change the resource name to your App's accent color - or any other color you want -->
  <meta-data android:name="com.dieam.reactnativepushnotification.notification_color" android:resource="@android:color/white"/>

<receiver android:name="com.dieam.reactnativepushnotification.modules.RNPushNotificationActions" />
    <receiver android:name="com.dieam.reactnativepushnotification.modules.RNPushNotificationPublisher" />
    <receiver android:name="com.dieam.reactnativepushnotification.modules.RNPushNotificationBootEventReceiver" android:exported="false">
        <intent-filter>
            <action android:name="android.intent.action.BOOT_COMPLETED" />
            <action android:name="android.intent.action.QUICKBOOT_POWERON" />
            <action android:name="com.htc.intent.action.QUICKBOOT_POWERON"/>
        </intent-filter>
    </receiver>`

**Important Note:**

- `node_modules\react-native\Libraries\PermissionsAndroid\PermissionsAndroid.js` permission handling.
  `const PERMISSIONS = Object.freeze({
  ...
  POST_NOTIFICATIONS: 'android.permission.POST_NOTIFICATIONS',
});`

`class PermissionsAndroid {
  PERMISSIONS: {|
    ...
    POST_NOTIFICATIONS: string,
  |} = PERMISSIONS;`

**Updating the Manifest:**

- Add the following line within the `<uses-permission>` section of your `AndroidManifest.xml` file:

  ```xml
  <uses-permission android:name="android.permission.POST_NOTIFICATIONS" />
  ```

**Troubleshooting:**

- Ensure you have followed the configuration steps for both libraries: `react-native-push-notification` and `react-native-date-picker`.
- Refer to their respective documentations for troubleshooting specific issues.
- If you encounter ANRs (Application Not Responding) errors, use Android Studio's profiling tools to identify bottlenecks in your code and optimize for performance.

**Feel free to contribute!**

We welcome contributions to this project. If you find any bugs or have suggestions for improvement, please submit a pull request.

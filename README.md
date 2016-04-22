#What is this?

This is a PhoneGap app that works with Estimote beacons. These are little bluetooth devices that send signals to your phone or tablet. The app can display a list of all detected beacons and which vicinity they're in: "immediate", "near", "far" or "unknown".

It relies on a number of plugins that are set in the config file, namely "PhoneGap-estimotebeacons", "cordova-plugin-whitelist" and "cordova-plugin-device". These plugins provide a way for us to access things like the phone's bluetooth functionality, battery level, camera and so on. The "PhoneGap-estimotebeacons" plugin takes care of all the hard work in detecting and ranging the beacons.

The app can be built into an apk package (for Android) or ipa package (for iOS) via the Adobe PhoneGap build website, https://build.phonegap.com.

To install the package on an Android device, transfer the file to an easy-to-locate folder on the phone, like "Download". Then on the phone, use a file explorer (like Astro) to open the file which will then automatically unpack it and install.

Installing on an Apple device is a bit more complicated because all iOS builds need to be signed by a developer certificate and require a provisioning profile that is tied to both your developer account and the device you wish to test on. This is quite a convoluted process, but the PhoneGap docs lay out the details well here, http://docs.build.phonegap.com/en_US/3.3.0/signing_signing-ios.md.html. Once that is all sorted, you install the package by connecting your device via the cable, opening up iTunes, clicking "File" then "Add to library", then choose the package, which will then show up in iTunes and can then be synced to the device.

Once you have the app installed, open up the "Range beacons" screen, and whenever a beacon is marked as in the "Near" range - it'll send a get request to the Raspberry Pi with the unique device id (uuid) as a GET parameter.


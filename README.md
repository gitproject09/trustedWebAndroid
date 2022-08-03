# [ Trusted Web - Android][published url]
## Developer: [Sopan Ahmed][instructor url]

Trusted Web - Android
---------------------

 * Trusted Web an alternative to Google chrome
 * If you have a Trusted Web Activity related question, the best place to ask it is on StackOverflow, on the
 [trusted-web-activity tag](https://stackoverflow.com/questions/tagged/trusted-web-activity), which is also
 monitored by the team.

------

### Debugging Digital Asset Links

As the debug certificate is different from the release one, and the fingerprint for debug should not be listed on the assetlinks.json file, is important to check if your Digital Asset Link is linked and verified.

After you generated your [signed APK](https://developer.android.com/studio/publish/app-signing#sign-apk). it can be installed into a test device, using adb:

``
adb install app-release.apk
``

If the verification step fails it is possible to check for error messages using the Android Debug Bridge, from your OS’s terminal and with the test device connected.

``
adb logcat | grep -e OriginVerifier -e digital_asset_links
``

If it is failing you'll see ``Statement failure matching fingerprint. Verification failed.`` message. Therefore is important to *review* *AndroidManifest.xml* and *build.gradle* files and check if the configurations are matching with the *assetlinks.json*.

Otherwise ``Verification succeeded.`` message should appear.

[published url]: https://github.com/gitproject09/trustedWebAndroid
[instructor url]: https://github.com/gitproject09

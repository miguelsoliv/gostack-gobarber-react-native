#### Libraries

* `styled-components` [dev dependency: `@types/styled-components`]
* `@react-navigation/native` [dependencies: `react-native-reanimated`, `react-native-gesture-handler`, `react-native-screens`, `react-native-safe-area-context`, `@react-native-community/masked-view`]
* `@react-navigation/stack`
* `react-native-vector-icons` [iOS: in `ios/myapp/Info.plist`, change/create `<key>UIAppFonts</key>` and add `<string>my-icon.ttf</string>` inside an `<array>` tag. Example:
```
...
  <key>UIAppFonts</key>
  <array>
    <string>Feather.ttf</string>
  </array>
</dict>
```
Android: at the end of the `android/app/build.gradle` add:
```
project.ext.vectoricons = [
  iconFontNames: ['my-icon.ttf']
];

apply from: "../../node_modules/react-native-vector-icons/fonts.gradle"
```
dev dependency: `@types/react-native-vector-icons`]
* `@unform/core`
* `@unform/mobile`
* `axios`
* `react-native-iphone-x-helper`
* `yup` [dev dependency: `@types/yup`]
* `@react-native-community/async-storage`

#### Custom font

* You can download a font family from [Google Fonts](https://fonts.google.com/)
* Make sure the name of the font file is the same as the PostScript name, which is viewable in the Font Book from iOS (Google Fonts probably uses the same name for both, so no need to worry)
* Put the files in the `assets/fonts` root folder (e.g. `myApp/assets/fonts/`)
* Create file `react-native.config.js` with:
```
module.exports = {
  project: {
    ios: {},
    android: {},
  },
  assets: [
    './assets/fonts/'
  ],
};
```
* `npx react-native link` or `yarn react-native link`
* If successful, Android will create `app/src/main/assets/fonts` and iOS will modify `ios/myapp/Info.plist` and include `<key>UIAppFonts</key>` at the end with your fonts

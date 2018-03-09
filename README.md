# react-native-prompt-android
A polyfill library for Alert.prompt on Android platform, working both on Android and iOS platform(iOS using [AlertIOS.prompt](http://facebook.github.io/react-native/docs/alertios.html#prompt))


### Installation

* Install from npm

```bash
npm i react-native-prompt-android --save
```

* Link native library

You can use react-native-cli:
```bash
react-native link react-native-prompt-android
```

Or rnpm:
```bash
rnpm link react-native-prompt-android
```

### Usage

```
import prompt from 'react-native-prompt-android';
prompt(
    'Enter password',
    'Enter your password to claim your $1.5B in lottery winnings',
    [
     {text: 'Cancel', onPress: () => console.log('Cancel Pressed'), style: 'cancel'},
     {text: 'OK', onPress: password => console.log('OK Pressed, password: ' + password)},
    ],
    {
        type: 'secure-text',
        cancelable: false,
        defaultValue: 'test',
        placeholder: 'placeholder'
    }
);
```

## Props

| Name                | Description                                                                       | Type    | Default                              |
|---------------------|-----------------------------------------------------------------------------------|---------|--------------------------------------|
| type                | Text input type: `'numeric', 'secure-text', 'phone-pad', 'email-address'`         | String  | 'default'                            |
| cancelable          |                                                                                   | Boolean | true                                 |
| defaultValue        | Default input value                                                               | String  |                                      |
| placeholder         |                                                                                   | String  |                                      |
| style               | `'default', 'shimo', 'cust'`                                                      | String  | 'default'                            |
| disableFullScreenUI | When in landscape mode, don't use fullscreen                                      | Boolean | false                                |
| highlightColor      | Color of text selection                                                           | String  | colorString or #RRGGBB or ##AARRGGBB |
| placeholderColor    | Color of the placeholder                                                          | String  | colorString or #RRGGBB or ##AARRGGBB  |
| color               | Color of the text                                                                 | String  | colorString or #RRGGBB or ##AARRGGBB  |
| buttonColor         | Color of the buttons                                                              | String  | colorString or #RRGGBB or ##AARRGGBB  |

Valid `colorString`: `'red', 'blue', 'green', 'black', 'white', 'gray', 'cyan', 'magenta', 'yellow', 'lightgray', 'darkgray', 'grey', 'lightgrey', 'darkgrey', 'aqua', 'fuchsia', 'lime', 'maroon', 'navy', 'olive', 'purple', 'silver', and 'teal'`

### "cust" Style (change underline, cursor, and handle color)
If you set this style, you can adjust the color of the "underline", "cursor", and "handles" of the input field. The default custom color is a reddish color of "#F34336". You can change this by going to `./node_modules/react-native-prompt-android/android/src/main/res/values/colors.xml` and changing the value of the `custUnderlineAndCursorAndHandleColor` field.

![Android Screen Shoot](./Example/android.png)

![Android Screen Shoot](./Example/ios.png)

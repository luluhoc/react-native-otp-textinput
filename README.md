### ADDED OPTION TO AUTOCOMPLET ON IOS AND ANDROID, BY THE WAY inputCellLength is limited for the moment

### REACT NATIVE OTP ULTIMATE

---

React Native Component that can used for OTPs and Pins as secure pin input.

[![npm version](https://badge.fury.io/js/react-native-otp-ultimate.svg)](https://badge.fury.io/js/react-native-otp-ultimate)
![npm downloads](https://img.shields.io/npm/dw/react-native-otp-ultimate.svg)

#### Installation

---

NPM

```
npm i -S react-native-otp-textinput
```

YARN

```
yarn add react-native-otp-textinput
```

#### Demo

---

<img src="ScreenShots/demo.gif" width="220px"><br>

#### How to Use

---

Check the `Example` react native app for usage.

#### Platform Support

---

Supports both Android and iOS.

#### Props

---

The following props are applicable for the component along with **props supported by react native `TextInput` component**

| Prop             | Type   | Optional | Default      | Description                                                                      |
| ---------------- | ------ | -------- | ------------ | -------------------------------------------------------------------------------- |
| defaultValue     | string | Yes      | ''           | Default Value that can be set based on OTP / Pin received from parent container. |
| handleTextChange | func   | Yes       | n/a          | callback with concated string of all cells as argument.
| onCodeFilled     | func   | Yes       | n/a          | when code is filled function returns the code so you can perform actions.
| inputCount       | number | Yes      | 4            | Number of Text Input Cells to be present.                                        |
| tintColor        | string | Yes      | #3CB371      | Color for Cell Border on being focused.                                          |
| offTintColor     | string | Yes      | #DCDCDC      | Color for Cell Border Border not focused.                                        |
| inputCellLength  | number | Yes      | 1            | Number of character that can be entered inside a single cell.                    |
| containerStyle   | object | Yes      | {}           | style for overall container.                                                     |
| textInputStyle   | object | Yes      | {}           | style for text input.                                                            |
| testIDPrefix     | string | Yes      | 'otp*input*' | testID prefix, the result will be `otp_input_0` until inputCount
| autoFillFromClipBoard     | boolean | Yes      | true | if should auto fill from clipboard on android


#### Helper Functions

---

Clearing and Setting values to component

```javascript
// using traditional ref
clearText = () => {
    this.otpInput.clear();
}

setText = () => {
    this.otpInput.setValue("1234");
}

render() {
    return (
        <View>
            <OTPTextInput ref={e => (this.otpInput = e)} >
            <Button title="clear" onClick={this.clearText}>
        </View>
    );
}
```

```javascript
// hooks
import React, { useRef } from 'react';

const ParentComponent = () => {
    const otpInput = useRef(null);

    const clearText = () => {
        otpInput.current.clear();
    }

    const setText = () => {
        otpInput.current.setValue("1234");
    }

    return (
        <View>
            <OTPTextInput ref={e => (otpInput = e)} >
            <Button title="clear" onClick={clearText}>
        </View> ̰
    );
}
```

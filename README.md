# react-native-multiplatform-settings

[![npm Version][npm-image]][npm-url]
[![License][license-image]][license-url]

React Native `Settings` module for both Android & iOS.

If this library has helped you, don't forget to give it a star :star2:

## Important

v2.1.0 works with Gradle 4.10.x, the default in React Native 0.58. If you are using Gradle 3.x please use react-native-multiplatform-settings 1.0.2

## Setup

```bash
yarn add react-native-multiplatform-settings
react-native link react-native-multiplatform-settings
```

## Usage

```js
import Settings from 'react-native-multiplatform-settings';

// Set a listener. It will be called for *each* value that has changed.
const watchId = Settings.watchKeys('strvar', () => {
  console.log('strvar changed.');
});

// If you never saved a value in "strvar", this is undefined.
console.log('restored setting:', Settings.get('strvar'));
// => undefined

// Store a value (only string, number, or boolean)
Settings.set({ strvar: 'First setting' });
console.log('new setting:', Settings.get('strvar'));
// => "First setting"

// You cann't remove a value, but you can set it to null.
// Next time your App start, the value will be undefined.
Settings.set({ strvar: null });
console.log('new setting:', Settings.get('strvar'));
// => null

// Store a new value, this will be preserved across sessions.
Settings.set({ strvar: 'final value' });

// => Don't forget to remove the listener
Settings.clearWatch(watchId)
```

## API

See React Native [Settings](https://facebook.github.io/react-native/docs/settings.html) page, the API is the same.

### Methods

- **get()**

  ```typescript
  static get(key: string) => number | string | value | null
  ```

- **set()**

  ```typescript
  static set(settings: { [key: string]: number | string | boolean | null } ) => void
  ```

- **watchKeys()**

  ```typescript
  static watchKeys(keys: string | string[], callback: () => any) => number
  ```

- **clearWatch()**

  ```typescript
  static clearWatch(watchId: number) => void
  ```

### NOTE

In Android, valid value types to store are `boolean`, `string`, and `number`.

If you pass `null` as value, the key will be removed in the next session.

If you want to save other types use the appropriate conversion:

```js
// Storing a Date object:
Settings.set({ myDate: new Date().toJSON() })
// Retrieve
const myDate = new Date(Settings.get('myDate'))

// Storing an array
Settings.set({ myArray: JSON.stringify([1,2,3]) })
// Retrieve
const myArray = JSON.parse(Settings.get('myArray') || '[]')
```

## Help improve the code

Of course, feedback, PRs, and stars are also welcome 🙃

Thanks for your support!

## License

The [MIT License](LICENSE) (MIT)

[npm-image]:      https://img.shields.io/npm/v/react-native-multiplatform-settings.svg
[npm-url]:        https://www.npmjs.com/package/react-native-multiplatform-settings
[license-image]:  https://img.shields.io/npm/l/express.svg
[license-url]:    https://github.com/relate-app/react-native-multiplatform-settings/blob/master/LICENSE

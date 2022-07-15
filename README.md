# react-native-copy-asset

[![npm version](https://badge.fury.io/js/react-native-copy-asset.svg)](https://badge.fury.io/js/react-native-copy-asset)
[![CircleCI](https://circleci.com/gh/ridvanaltun/react-native-copy-asset/tree/master.svg?style=shield)](https://circleci.com/gh/ridvanaltun/react-native-copy-asset/tree/master)

## Link and unlink assets to your react-native project with ease!

## Advantages

- `react-native link` only supports font files, this tool supports all assets.
- Unlinking is automatic when you delete an asset, with `react-native link`, you need to unlink the files manually.
- Proper link (and unlink) for `mp3` (to use with [`react-native-sound`](https://github.com/zmxv/react-native-sound#basic-usage)) and `ttf` files.

### [Check out this starter-kit to use your assets with even more simplicity.](https://github.com/ridvanaltun/react-platformula-boilerplate)

## Usage

- Install
  ```bash
  npm install -g react-native-copy-asset
  # or yarn
  yarn global add react-native-copy-asset
  ```
- Add assets to your `react-native.config.js` as you would with `react-native link`
  ```json
  ...
   "assets": [
      "./src/font",
      "./src/mp3"
    ]
  ```
- Run the command and linking + unlinking is automatic!
  ```bash
  react-native-copy-asset
  ```

## Explanation

With `react-native link` you have to unlink the files manually, which is hard work.  
Instead this library writes `link-assets-manifest.json` to the root of `android` and `ios` folders to keep track of the files which it added, for later removing it for you if missing from your `assets`!

## Parameters

- `-p, --path` - path to project, defaults to cwd.
- `-a, --assets` - assets paths, for example `react-native-copy-asset -a ./src/font ./src/mp3`.
- `-ios-a, --ios-assets` - ios assets paths, will disable android linking
- `-android-a, --android-assets` - android assets paths, will disable ios linking.
- `-n-u, --no-unlink` - Not to unlink assets which not longer exists, not recommanded.

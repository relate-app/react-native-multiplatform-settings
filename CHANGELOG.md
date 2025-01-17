# react-native-multiplatform-settings changes

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

## [2.2.0] - 2022-08-10

- Updated dependencies
- Renamed package from react-native-cross-settings to react-native-multiplatform-settings

## [2.1.0] - 2019-05-20

### Changed

- Updated Android Tools to v28.x
- Using gradle 4.10.2

### Fixed

- Minor errors in build.gradle

### Added

- Markdownlint config
- Ko-fi link

## [2.0.1] - 2018-10-09

### Fixed

- Fix error in build.gradle

## [2.0.0] - 2018-10-09

This is the first version for Gradle 4.4

### Added

- Runtime check in debug mode for the type of values to store.

### Changed

- The id of `watchKeys` and `clearWatch` is number, the callback returns void.

## [1.0.2] - 2018-09-17

### Changed

- The changelog follows the format on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/).
- Simplifies the reading of variables in android/build.gradle

### Fixed

- The callback of `watchKeys` is not called.

## [1.0.1] - 2018-03-19

### Fixed

- Missing google repository in android/gradle (for development).

## [1.0.0] - 2018-03-19

### Added

- Flow types (not sure if correctly).

### Changed

- The default `buildToolsVersion` was changed 26.0.3 and `compileSdkVersion`/`targetSdkVersion` to 26.
- Better support for `long` & `double` values (the range of `long` is still limited by the RN Bridge).

### Removed

- react-native from peerDependencies, since this library must work in versions prior to 0.50.

## [0.2.0] 2018-03-19

### Changed

- Changed minSdkVersion version to 16 - Thanks to @wayne1203
- The preferences file is openning only when used.

# Flutter Template

This project is a starter Flutter application with preconfigured Fastlane lanes for Android and iOS release workflows.

## Getting Started

```bash
flutter pub get
flutter run
```

## Fastlane

This template includes:
- `Gemfile` with Fastlane dependency
- `android/fastlane/Fastfile` and `android/fastlane/Appfile`
- `ios/fastlane/Fastfile` and `ios/fastlane/Appfile`

### 1. Install Ruby dependencies

```bash
bundle install
```

### 2. Configure local Fastlane values (not committed)

```bash
cp android/fastlane/.env.example android/fastlane/.env
cp ios/fastlane/.env.example ios/fastlane/.env
```

Then edit the `.env` files with your real package/bundle/team values.

### 3. Android lanes

```bash
cd android
bundle exec fastlane test
bundle exec fastlane build_release
bundle exec fastlane build_apk
```

Optional Play Store upload lanes:
- `internal`
- `deploy`

Before using upload lanes:
- Set real values in `android/fastlane/.env`
- Add `android/play-store-service-account.json` (ignored by git)

### 4. iOS lanes

```bash
cd ios
bundle exec fastlane test
bundle exec fastlane build_release
bundle exec fastlane build_ipa
```

Optional App Store lanes:
- `beta`
- `release`

Before using upload lanes:
- Set real values in `ios/fastlane/.env`
- Configure iOS signing configuration/certificates in Xcode

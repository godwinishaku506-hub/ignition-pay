# App Store and Play Store Setup

This document captures the repository-side preparation for publishing Ignition Pay on Apple App Store Connect and Google Play Console.

## 1. App Store Connect (iOS)

### Create the app record
- Sign in to App Store Connect.
- Create or select the team/account that will own the app.
- Create a new app record for Ignition Pay.
- Set the bundle identifier to the value used by the iOS app target.
- Choose the primary language and SKU.

### Configure release channels
- Create a production release candidate once the build is ready.
- Add internal testers and external testers as needed.
- Prepare a release submission checklist for review.

### Fill metadata
- App name
- Subtitle
- Promotional text
- Description
- Keywords
- Privacy policy URL
- Support URL
- Marketing URL
- Category and age rating

### Prepare screenshots
- Capture screenshots for the required iPhone and iPad sizes.
- Store them in the project folder for later upload.

## 2. Google Play Console (Android)

### Create the app record
- Sign in to Google Play Console.
- Create a new app entry for Ignition Pay.
- Set the default language and app category.
- Link the app to the correct Google Play signing configuration.

### Configure release channels
- Create an internal testing track.
- Add closed testing and open testing tracks as release stages.
- Promote builds from internal -> closed -> open once approved.

### Fill metadata
- App title
- Short description
- Full description
- Feature graphic
- Phone and tablet screenshots
- Privacy policy URL
- Support URL
- Contact email
- Category and tags

## 3. Repository checklist

### Required assets
- App icon
- Privacy policy URL
- Support URL
- App store screenshots
- Play Store feature graphic

### Suggested folder layout
- [ignition-mobile/docs/screenshots/ios](screenshots/ios)
- [ignition-mobile/docs/screenshots/android](screenshots/android)

### Metadata template
Use the metadata template in [ignition-mobile/docs/store-metadata-template.json](store-metadata-template.json) as the starting point for both stores.

## 4. Release notes template
- What changed in this version
- New features and fixes
- Known limitations
- Security or compliance notes

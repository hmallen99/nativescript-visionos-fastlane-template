# nativescript-visionos-fastlane-template

This repository contains an example of a fastlane setup for deploying VisionOS NativeScript projects with GitHub Actions. This serves as an addendum for the NativeScript fastlane tutorial: https://blog.nativescript.org/automatic-nativescript-app-deployments-with-fastlane/.

## Prerequisites

1. Create a greenfield NativeScript VisionOS project by following the instructions here: https://docs.nativescript.org/guide/visionos
2. Read through the iOS fastlane deployment instructions here: https://blog.nativescript.org/automatic-nativescript-app-deployments-with-fastlane/.

## Fastlane setup

1. Copy the Gemfile in the root of this repository to your repository:
2. Run the following command in your repository. This should install fastlane and the necessary dependencies for NativeScript.

```
bundle install
```

3. Run `fastlane init` in the root of your repository. This will generate a folder `fastlane` with a `Fastfile`. You can overwrite this `Fastfile` with the one from the root of this repository. This file is very similar to the one in the NativeScript fastlane tutorial, with some changes to get things working with VisionOS.
4. Run `fastlane match init`. This will walk you through some steps to generate a `Matchfile` similar to the one in this repository. I recommend choosing "Git" as the storage mode.

## Local environment setup

1. If you only want to build distribution bundles locally, you can copy the `.env.default` file from this repo to the root of your repository. It is highly recommended to add this file to your .gitignore.
2. Run `fastlane visionos beta` to upload a build directly to TestFlight.

## GitHub Actions setup

1. Copy `.github/workflows/publish.yaml` to your GitHub Actions workflow folder.
2. Navigate to the "Actions" tab in your GitHub repository and run the "Build VisionOS App" workflow from your desired branch.

## Further reading

- Using the App Store Connect API: https://medium.com/swiftable/build-and-deploy-the-app-to-testflight-using-github-actions-with-fastlane-and-app-distribution-ff1786a8bf72
- Understanding App Store provisioning and GitHub actions setup: https://www.andrewhoog.com/post/how-to-build-an-ios-app-with-github-actions-2023/
- Fastlane docs: https://docs.fastlane.tools/getting-started/ios/setup/

# Cornell AppDev Fastlane Guide

## Setup

0. Make sure `xcode-select --install` has been run.

1. Install fastlane

	`sudo gem install fastlane -NV`

If your computer's ruby version is not high enough...

	brew update
	brew install rbenv ruby-build
	rbenv install --list

Choose the latest stable version (2.4.2) and then...
  
	rbenv install [Latest Stable Version]
  
## Integrating with your iOS Project

1. Run `fastlane init` at the root directory of your project.
2. Enter `/fastlane`, and replace **Fastfile** with this repository's version.
3. Replace **Appfile** with the given file (contains sensitive information!)
4. Modify Appfile for the current project

**Bonus: Beta Tester Sign Up Website**

Using AppDev's Heroku account, follow the **Getting Started** guide [here](https://github.com/fastlane/boarding).

**Bonus: Slack Integration**

1. Go to [Custom Integrations](https://cornellappdev.slack.com/apps/manage/custom-integrations) on Slack. 
2. WebHooks > Add Configuration
3. Obtain a hooks.slack.com URL, and modify your Appfile accordingly.

## Deploy to Testflight

`fastlane ios beta changelog:"Awesome release notes"`

**Important:** If you are deploying for the first time, append `initial:true` 

You will need an iPhone Distribution certificate to deploy. If you haven't already...
1. Xcode > Preferences > Accounts > [AppDev Account] > Manage Certificates > Add iOS Distribution
2. If an error is thrown, have a teammate export the certificate and private key from Keychain Access.


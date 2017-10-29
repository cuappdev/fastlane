# Cornell AppDev Fastlane Guide (WIP)

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

## Deploy to Testflight

`fastlane ios beta changelog:"Awesome release notes"`

### Adding App Details

1. Change the appropriate details in Appfile

**Slack Integration**

2. Go to [Custom Integrations](https://cornellappdev.slack.com/apps/manage/custom-integrations) on Slack. 
3. WebHooks > Add Configuration
4. Obtain a hooks.slack.com URL, and paste in your Appfile

### Beta Testing Sign-Up Form

1. Using AppDev's Heroku account, follow the **Getting Started** guide [here](https://github.com/fastlane/boarding)



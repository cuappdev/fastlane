# Cornell AppDev x Fastlane

How to use [fastlane](fastlane.tools) ([docs](docs.fastlane.tools)) on your latest Cornell AppDev project.

## Installation

**Install fastlane**

````
sudo gem install fastlane -NV
````

See **Troubleshooting** if you get an error that your version of Ruby isn't high enough.

**Setup Gemfile**

````
sudo gem install bundler
bundle update
````
  
## Integrating with your iOS Project

Edit the variables in `fastlane/Appfile` to match your project.

**Slack Integration**

1. Go to [Custom Integrations](https://cornellappdev.slack.com/apps/manage/custom-integrations) on Slack. 
2. WebHooks > Add Configuration
3. Obtain a hooks.slack.com URL, and modify your Appfile accordingly.

**Beta Tester Sign Up Website**

Using AppDev's Heroku account, follow the **Getting Started** guide [here](https://github.com/fastlane/boarding).

## Deploy to Testflight

`bundle exec fastlane ios beta changelog:"Awesome release notes"`

**Important:** If you are deploying for the first time, append `initial:true` to the above command.

You will need an iPhone Distribution certificate to deploy. If you haven't already...
1. Xcode > Preferences > Accounts > [AppDev Account] > Manage Certificates > Add iOS Distribution
2. If an error is thrown, have a teammate export the certificate and private key from Keychain Access.

## Troubleshooting

### Fastlane Installation Issues (Updating Ruby)

If your computer's ruby version is not high enough...

	brew update
	brew install rbenv ruby-build
	rbenv install --list

Choose the latest stable version (2.4.2) and then...
  
	rbenv install [Latest Stable Version]


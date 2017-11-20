# Cornell AppDev x Fastlane

How to use [fastlane](https://fastlane.tools) on your latest Cornell AppDev project.

## Installation

**Install fastlane**

````
sudo gem install fastlane -NV
````

See **Troubleshooting** if you get an error at this step. (Ruby version >= 2.1)

**Install bundler**

````
sudo gem install bundler
````
  
## Integrating with your iOS Project

1. Clone this repository in your project's root directory. Move **Gemfile** out of `fastlane/` to the root directory.
2. Run `sudo bundle update`
3. Modify the variables in `fastlane/Appfile` for your project.

**Slack Integration**

1. Go to [Custom Integrations](https://cornellappdev.slack.com/apps/manage/custom-integrations) on Slack. 
2. WebHooks > Add Configuration
3. Obtain a hooks.slack.com URL, and modify your Appfile accordingly.

**Beta Tester Sign Up Website**

Using AppDev's Heroku account, follow the **Getting Started** guide [here](https://github.com/fastlane/boarding).

## Deploy to Testflight

#### First Deployment

````
bundle install
bundle exec fastlane ios beta initial:true changelog:"Awesome release notes"
````

#### Typical Use

````
bundle exec fastlane ios beta changelog:"Awesome release notes"
````

#### Notes

Make sure your .gitignore file for your project includes some or all of the following
- `*.mobileprovision`
- `*.dSYM.zip`
- `*.ipa`
- `*.cer`

You will need an iPhone Distribution certificate to deploy. If you haven't already...
1. Xcode > Preferences > Accounts > [AppDev Account] > Manage Certificates > Add iOS Distribution
2. If an error is thrown, have a teammate export the certificate and private key from Keychain Access.

## Troubleshooting

[**GitHub**](https://github.com/fastlane) • [**Docs**](https://docs.fastlane.tools)

### Fastlane Installation Issues (Updating Ruby)

If your computer's ruby version is not high enough...

	brew update
	brew install rbenv ruby-build
	rbenv install --list

Choose the latest stable version (2.4.2) and then...
  
	rbenv install [Latest Stable Version]


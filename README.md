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

1. Clone this repo inside the root directory of your project.

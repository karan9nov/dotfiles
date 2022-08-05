# Setting up mac for the first time

1. Install brew - [Homebrew](https://brew.sh/)

	Copy this ruby script and run in your terminal - 
	
	```
	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
	```
2. Install Python 3 and AWS CLI
	
	```
	brew install python3
	brew install awscli
	```
	
	Configure AWS CLI
	
	```
	aws configure
	```
	This will ask you for AWS Access Key and Secret Key. You should have them from the very first time when you set up your AWS Account. If you dont have them contact your admin to create a new set of keys for you. 
	
3. Install some useful apps (Casks) - 

	```
	brew install --cask iterm2 				# iTerm 2 - replacement for Mac Terminal
	brew install --cask sublime-text		# Text editor
	brew install --cask google-chrome		# Google Chrome Browser
	brew install --cask fliqlo				# Fliqlo Screen Saver
	brew install --cask slack				# Slack
	brew install --cask intellij-idea		# IntelliJ IDEA
	brew install --cask datagrip			# DataGrip
	brew install --cask google-drive		# Google Drive Mac Client
	brew install --cask itsycal				# Itsycal
	brew install --cask tunnelblick			# VPN Client
	brew install --cask postman
	brew install --cask whatsapp
	brew install --cask monitorcontrol		# Handy app to change external monitors brightness
	brew install --cask docker
	brew install --cask macdown				# Markdown Editor
	```	

4. Change some of the macOS defaults

	Add spaces in dock

	```
	defaults write com.apple.dock persistent-apps -array-add '{"tile-type"="spacer-tile";}' && killall Dock
	```
	Autohide dock
	
	```
	defaults write com.apple.dock "autohide" -bool "true" && killall Dock
	```

	Instantly reveal and hide dock (0 delay)
	
	```
defaults write com.apple.dock "autohide-delay" -float "0" && killall Dock
	```

	Change the default location of screenshots
	
	```
	defaults write com.apple.screencapture "location" -string "~/Screenshots" && killall SystemUIServer
	```
	
	Do not show thumbnail after screenshot is taken
	
	```
	defaults write com.apple.screencapture "show-thumbnail" -bool "false"
	```
	
	Change screenshot type from PNG to JPEG
	
	```
	defaults write com.apple.screencapture "type" -string "jpg" 
	```
	
	Show all file extensions in Finder
	```
	defaults write NSGlobalDomain "AppleShowAllExtensions" -bool "true" && killall Finder
	```
	
	Disable Auto Organize Mac Spaces
	
	```
	defaults write com.apple.dock "mru-spaces" -bool "false" && killall Dock
	```
	

	
	
# Setting up mac for the first time

1. Default shell is `zsh`, but I like `bash` just because I have been using it for a long time and I am comfortable with it. 

	To verify the shell, run:
	```echo $0```

	If it is `bash`, you are good. To change it to `bash`, run:
	```
	chsh -s /bin/bash
	```
	
7. Install `oh-my-bash` - Follow the instructions [here](https://github.com/ohmybash/oh-my-bash/blob/master/README.md). My preferred theme to use is `bakke`.

2. Install brew - [Homebrew](https://brew.sh/)

	Copy this ruby script and run in your terminal - 
	```
	/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
	```
	After this is done, run this in your terminal. This will add `homebrew` to PATH
	```
	echo "export PATH=/opt/homebrew/bin:\$PATH" >> ~/.bashrc
	```

3. Install basic command line stuff
	```
	brew install python3
	brew install wget
	```
	
4. Install some useful apps (Casks) - 
	```
	brew install --cask amazon-chime
	brew install --cask datagrip
	brew install --cask docker
	brew install --cask fliqlo
	brew install --cask google-chrome
	brew install --cask google-drive
	brew install --cask hiddenbar
	brew install --cask intellij-idea
	brew install --cask iterm2 
	brew install --cask itsycal
	brew install --cask microsoft-office
	brew install --cask microsoft-teams
	brew install --cask monitorcontrol
	brew install --cask postman
	brew install --cask slack
	brew install --cask sublime-text
	brew install --cask todoist
	brew install --cask tunnelblick
	brew install --cask visual-studio-code
	brew install --cask whatsapp
	brew install --cask zoom
	```	

	For tunnelblick, to disable auto startup on login - 
	```
	defaults  write  net.tunnelblick.tunnelblick  doNotLaunchOnLogin  -bool  yes

	```

5. Change some of the macOS defaults

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

6. Install JDK and Maven

	[Video](https://www.youtube.com/watch?v=s-c4MmEGFjI)

	[Blog](http://programhub.net/install-android-studio-on-apple-silicon-m1-m1-pro-m1-max-macbooks/)

	After JDK is installed, set the `JAVA_HOME` in your `~/.bashrc` file. 
	```
	export JAVA_HOME=/Library/Java/JavaVirtualMachines/zulu-8.jdk/Contents/Home
	```

	Also install maven using homebrew.
	```
	brew install maven
	```

7. Install and Configure AWS CLI

	```
	brew install awscli
	```
	```
	aws configure
	```
	This will ask you for AWS Access Key and Secret Key. You should have them from the very first time when you set up your AWS Account. If you dont have them contact your admin to create a new set of keys for you. 

8. Install `jenv` to manage java environments.

	```
	brew install jenv
	```

	Copy this to your `~/.bashrc` file. 
	```
	# SETTING UP JENVs
	export PATH="$HOME/.jenv/bin:$PATH"
	eval "$(jenv init -)"
	```

	Then run the following to make sure your `JAVA_HOME` is set. 
	```
	jenv enable-plugin export
	exec $SHELL -l
	```

	Finally set your `JAVA_HOME`
	```
	jenv add "$(/usr/libexec/java_home)"
	```

	For further read [this](https://github.com/jenv/jenv#readme).

9. 

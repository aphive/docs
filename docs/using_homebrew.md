## Xcode
Before doing anything you will need to have Xcode installed on your Mac.

### Install Xcode
```
xcode-select --install
```

## Homebrew
Homebrew is a package manager designed for installing UNIX tools and other open-source applications on your Mac.

### Install Homebrew
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"
```

### Bash Config
To make things easier for myself I add the following to my profile:
```
alias brewup='brew update; brew upgrade; brew cleanup; brew doctor'
```

This allows you to run `brewup` so that you can keep things updated and clean without having to run several commands.

### Using Homebrew

#### Searching for applications
```
brew search app_name
```

#### Installing Applications
```
brew install app_name
```

#### Uninstall Applications
```
brew remove app_name
```

#### Get information on an Application
```
brew info app_name
```

## Cask
Cask extends Homebrew and is used to install graphical apps on your mac like Google Chrome. You must install Homebrew first.

### Using Cask

#### Searching for apps
```
brew install caskroom/cask/brew-cask
```

#### Install Applications
```
brew cask install app_name
```

#### Uninstall Applications
```
brew cask uninstall app_name
```

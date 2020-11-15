The default Bash that comes on your Mac is decades old, To get the newest version follow these instructions.

**Note**: the following instructions don’t change the old version of Bash, but rather install a new version and set it as the default. The two versions will exist side by side on your system but you can ignore the old version.


* Make sure you have Homebrew installed, see [here](../using_homebrew) to get it if you don't already.

## Install bash
```
brew install bash
```

## Checking installed versions
* Make sure we see both the old and the new by running `which -a bash`:
```
/usr/local/bin/bash
/bin/bash
```
* Running `/usr/local/bin/bash --version` will return the following:
```
GNU bash, version 5.0.0(1)-release (x86_64-apple-darwin18.2.0)
Copyright (C) 2019 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>

This is free software; you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
```
* Running `/bin/bash --version` will return the following:
```
GNU bash, version 3.2.57(1)-release (x86_64-apple-darwin18)
Copyright (C) 2007 Free Software Foundation, Inc.
```
## Allowing the new Bash
* Open your shells file for editing:
```
sudo vi /etc/shells
```
* Add `/usr/local/bin/bash` to the file.
* Change the default shell to use the new bash:
```
chsh -s /usr/local/bin/bash
```
## Final verification
* Close your terminal and restart it then run `echo $BASH_VERSION` to verify the changes worked:
```
5.0.0(1)-release
```

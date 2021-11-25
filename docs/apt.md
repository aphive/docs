# APT (Advanced Packaging Tool)

APT was born out of a need for a better way to handle packages that users install on their machines.
In the beginning one would use `.tar.gz.` but when Debian made it on the scene, it introduced `dpkg`
as the method to manage packages on GNU/Linux machines. As need for a faster, more efficient way to
install packages that would also handle dependencies and manage configuration files the APT system
we know today was born. Debian took lead in both of these revolutionary leaps in history.

Apt stores a list of repositories or software channels in the file `/etc/apt/sources.list`
and in any file with the suffix `.list` under the directory `/etc/apt/sources.list.d/`

## debian-ubuntu-repos

Repos for Ubuntu and Debian

* These are for Debian and Ubuntu Distros that are still supported only.
* We will keep these updated as new releases are made and old ones are no longer supported.

### Before you make changes

Install these packages:

```
apt install curl wget apt-transport-https dirmngr
```

### Making the Changes

* Open a terminal
* Backup your original sources file:
```
mv /etc/apt/sources.list /etc/apt/sources.list.orig
```
* Create a new sources file:
```
vi /etc/apt/sources.list
```
* Paste in the sources info you will be using

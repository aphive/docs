# Ubuntu Apt Sources

We will only keep supported Releases.

Make sure to install these:

```
sudo apt install curl wget apt-transport-https dirmngr
```

## Ubuntu 22.04 Jammy Jellyfish

Will be updated once released.

## Ubuntu 20.04 Focal Fossa

Supported until April 2030

```
#------------------------------------------------------------------------------#
#                            OFFICIAL UBUNTU REPOS                             #
#------------------------------------------------------------------------------#

###### Ubuntu Main Repos
deb http://archive.ubuntu.com/ubuntu/ focal main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal main restricted universe multiverse

###### Ubuntu Update Repos
deb http://archive.ubuntu.com/ubuntu/ focal-updates main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ focal-security main restricted universe multiverse
deb http://archive.ubuntu.com/ubuntu/ focal-backports main restricted universe multiverse

deb-src http://archive.ubuntu.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-security main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-backports main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ focal-proposed main multiverse restricted universe
```

## Ubuntu 18.04 LTS Bionic Beaver

Supported until April 2028

```
#------------------------------------------------------------------------------#
#                            OFFICIAL UBUNTU REPOS                             #
#------------------------------------------------------------------------------#


###### Ubuntu Main Repos
deb http://us.archive.ubuntu.com/ubuntu/ bionic main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ bionic main restricted universe multiverse

###### Ubuntu Update Repos
deb http://us.archive.ubuntu.com/ubuntu/ bionic-security main restricted universe multiverse
deb http://us.archive.ubuntu.com/ubuntu/ bionic-updates main restricted universe multiverse
deb http://us.archive.ubuntu.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb http://us.archive.ubuntu.com/ubuntu/ bionic-backports main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ bionic-security main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ bionic-updates main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ bionic-proposed main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ bionic-backports main restricted universe multiverse
```

## Ubuntu 16.04 LTS Xenial Xerus

Supported until April 2026.

```
#------------------------------------------------------------------------------#
#                            OFFICIAL UBUNTU REPOS                             #
#------------------------------------------------------------------------------#


###### Ubuntu Main Repos
deb http://us.archive.ubuntu.com/ubuntu/ xenial main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ xenial main restricted universe multiverse

###### Ubuntu Update Repos
deb http://us.archive.ubuntu.com/ubuntu/ xenial-security main restricted universe multiverse
deb http://us.archive.ubuntu.com/ubuntu/ xenial-updates main restricted universe multiverse
deb http://us.archive.ubuntu.com/ubuntu/ xenial-proposed main restricted universe multiverse
deb http://us.archive.ubuntu.com/ubuntu/ xenial-backports main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ xenial-security main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ xenial-updates main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ xenial-proposed main restricted universe multiverse
deb-src http://us.archive.ubuntu.com/ubuntu/ xenial-backports main restricted universe multiverse

###### Ubuntu Partner Repo
deb http://archive.canonical.com/ubuntu xenial partner
deb-src http://archive.canonical.com/ubuntu xenial partner
```

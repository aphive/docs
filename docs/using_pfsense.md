# Using pfSense

> pfSense® software is a free, open source customized distribution of FreeBSD specifically tailored for use as a firewall and router that is entirely managed via web interface. In addition to being a powerful, flexible firewalling and routing platform, it includes a long list of related features and a package system allowing further expandability without adding bloat and potential security vulnerabilities to the base distribution.

> The pfSense project is hosted and developed by Rubicon Communications, LLC ([Netgate](https://www.netgate.com/)).

## Introduction

I used to rent Comcast's modem but after encountering issues after issues after issues, I decided to stop renting and buying my own modem and a NetGear Nighthawk router. I ran that for some years then I was introduced to pfSense by one of my co-workers. I had an older computer lying around that I was going to get rid of so I decided to install pfSense and give it a run and build my own gateway to manage my network.

!!! note
    * Keep in mind that:
        * this is my personal experience and use case so yours may vary
        * this is **not** a definitive tutorial of any kind or in any way
        * I am **not** a network or security professional so there will be different ways to do the things I do or better ways altogether

If you have any suggestions, feel free to:
[Submit an Issue](https://github.com/aphive/docs/issues){: .md-button }.

## Getting pfSense

Get pfSesne from their [Downloads](https://www.pfsense.org/download/) page.

If you are using your own computer to do this project, you will want to select:

* Architecture: `AMD64 (64-bit)`
* Installer: `USB Memstick Installer`
* Console: `VGA`
* Mirror: leave default (`New York City, USA`)

Once you've downloaded the file, it is strongly recommended to run a checksum against it to ensure it's a legit and secure file.

What is a Checksum you ask? A checksum is a small-sized datum from a block of digital data for the purpose of detecting errors which may have been introduced during its transmission or storage.

To verify integrity, use the info under the download button, it will look like this:

```
SHA256 Checksum for compressed (.gz) file:
aa40595d090465f20fff1890092e6a14a753cd9486ccc7101d81301cad8b8840
```

I use MacBook so you will need to look up how to do this for your OS.

* Launch Terminal
* cd into the directory you downloaded the file into and run this command

```
sha256sum pfSense-CE-memstick-2.4.5-RELEASE-p1-amd64.img.gz
```

which should return the following:

```
aa40595d090465f20fff1890092e6a14a753cd9486ccc7101d81301cad8b8840  pfSense-CE-memstick-2.4.5-RELEASE-p1-amd64.img.gz
```

Notice how the output is the same as what is listed on the site.

Now that we have that out of the way, you will want to extract the contents.

## Creating an Install USB

I use [Balena Etcher](https://www.balena.io/etcher/) to create my install USB drives.

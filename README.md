# Homebrew Buildit Setup

This [Tap](https://github.com/Homebrew/brew/blob/master/docs/How-to-Create-and-Maintain-a-Tap.md) 
is intended to provide an easier way to configure new Macs (i.e. a Mac that has just had its OS fresh installed) 
instead of following multiple Confluence steps.


## Context 

Initially it was intended to be using brew [Formula](https://github.com/Homebrew/brew/blob/master/docs/Formula-Cookbook.md) 
to accomplish this task, but Formulas seems to have a limitation in regards to dependencies: 
a Formula can't depend on a [Cask](https://github.com/caskroom/homebrew-cask/blob/master/USAGE.md).
For this reason, the approach was changed to use Casks instead of Formulas. 

Currently, all the setup is done using existing Formulas or Casks, so the Casks provided here does not install
any Mac App by itself as is expected of Brew Casks, instead it relies on a list of dependencies
for other Formulas and Casks to make sure that everything that is needed is indeed installed on the Mac.

## How to use

First it is necessary to install Homebrew. Information on how this can be done can be found [here](https://brew.sh/)

To make use of these Casks, is is needed to add the Buildit Tap to your local Homebrew.
This can be done with the following command:

```
brew tap buildit/homebrew-buildit-setup
```

After this, your Homebrew will be configured to "see" the Buildit tap with all its available Formulas and Casks.
Also, it will be updated/upgraded with the usual ``home brew update / upgrade`` commands.

## What is available

### Build Base Tools

This Cask is intended to install the base tools, not making a differentiation on programming
languages/environments. It can be installed using the command ``brew cask install buildit-base-tools``

The following Casks and Formulas will be installed together with this Cask:

* Git (Formula)
* Bash Completion (Formula)
* Python (Formula)
* Ansible (Formula)
* Terraform (Formula)
* AWS CLI (Formula)
* Packer (Formula)
* Docker (Formula)
* Chromedriver (Formula)
* Dropbox (Cask)
* Google Chrome (Cask)
* Firefox (Cask)
* Atom (Cask)
* Skype (Cask)
* Slack (Cask)
* Tunnelblick (Cask)
* Vagrant (Cask)

### Buildit Java Based Tools

This Cask is intended to install the Java based tools. It can be installed using the command ``brew cask install buildit-java-based-tools``.

The following Casks and Formulas will be installed:

* Maven (Formula)
* Gradle (Formula)
* Tomcat (Formula)
* Java 9 (Cask)
* Java 8 (Cask)
* Java 7 (Cask)

### Notes

As a note, it is important to note that if any of the above Casks have already been installed without using
Homebrew, it will break the installation (default behaviour for any Cask).

At the end of the installation, there will be information about the manual steps needed to configure
each "package" of Casks. Please pay attention to it.

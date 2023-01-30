# wire for UNIX

## Introduction

wire is a command line client for the Wired 2.0 + 2.5 protocol.

## Install wire (UNIX-like systems)

This tutorial explains how to install and run wire on an UNIX-like operating system.

### Howto install on:

**Ubuntu/Debian10 and higher only**

	sudo apt-get install -y build-essential autoconf git libxml2-dev libssl-dev zlib1g-dev libreadline-dev libcurl4-gnutls-dev

**Fedora**
	
	sudo yum -y install git libtool openssl-devel sqlite-devel libxml2-devel zlib-devel readline-devel libcurl-devel autoconf gcc make

**CentOS**

	sudo yum install epel-release
	sudo yum -y install git libtool openssl-devel sqlite-devel libxml2-devel zlib-devel readline-devel libcurl-devel autoconf gcc make

**openSUSE**

	sudo zypper install libtool libopenssl-devel sqlite3-devel libxml2-devel zlib-devel readline-devel libcurl-devel autoconf gcc make
	
### Getting started

Installing wire from sources will be done using the Autotools standard (configure, make, make install).

##### 1. Get wire sources via Terminal:

	git clone https://github.com/ProfDrLuigi/wire

Then move to the `wire` directory:

	cd wire/

Initialize and update submodules repositories:

	git submodule update --init --recursive --remote
	libwired/bootstrap

Then check that the `libwired` directory was not empty and `configure` file exists.

##### 3. Run the configuration script:

During the configuration, scripts will check that your environment fills the requirements described at the top of this document. You will be warned if any of the required component is missing on your operating system.

To start configuration, use the following command:

	./configure

wire is designed to be installed into `/usr/local/bin` by default. To change this, run:

	./configure --prefix=/path	

If you installed OpenSSL in a non-standard path, use the following command example as reference:

	env CPPFLAGS=-I/usr/local/opt/openssl/include LDFLAGS=-L/usr/local/opt/openssl/lib ./configure

Use `./configure --help` in order to display more options.

This will require write permissions to `/usr/local/bin`, or whatever directory you set as the prefix above. Depending of your OS setup, you may require to use `sudo`.

##### 4. Compile and install Binary
	make
	sudo make install
	
Don't forget to put your credentials into ~/.wire/config before you start the bot the first time.

##### 5. Running wire

To start the installed wire, run:

	/usr/local/bin/./wire

##### 6. Configuration

Default path for the configuration file is:

	~/.wire/config
	
Example configuration:

	charset UTF-8
	open -l USER -p PASSWORT -P PORT URL
	nick YOUR_NAME
	status YOUR_STATUS
	icon /home/YOUR_USER/.wire/PICTURE.png
	
If you want to know the available commands of the wire type

	/help
	
in the Chat Main window.

If you got/send a msg you can cycle through the windows with:

### Troubleshootings

This implementation of the Wired 2.0/2.5 protocol is not compliant with the version of the protocol distributed by Zanka Software, for several deep technical reasons.

CONTRIBUTORS
============

- Erik Tengblad
- christ25

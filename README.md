# Tomcat / TomEE CLI frontend

## Overview

This repository contains a command line utility named `tomcat` which provides a single point of access to manage a Tomcat server
and its configuration option. This utility can be used in lieu of the many `*.sh` files found in a standard Tomcat or TomEE
distribution.

You will want to use this utility if you want to:

  - have a single front-end utility to manage your Tomcat server
  - configure multiple JDK/JRE Java environments
  - manage multiple Tomcat runtime environments
  - manage the update of your webapps
  - regularly create snapshots of your Tomcat configuration
  - support legacy Tomcat versions (e.g. Tomcat 6)

All that this utility requires are common POSIX commands, including a valid KornShell. This utility has dropped the support for
Cygwin, OS400 and Windows, as available in standard Tomcat / TomEE distributions. The gold master is developped on macOS and
production environments are run on Amazon Linux and CentOS; it is forseen that only minor adjustements may be required to operate
this on other POSIX/UNIX or Linux distributions.

This utility is currently customised for the [SAMinfo ERP](http://saminfo.ch) for which it is primarily intended. This can be
easily changed by changing the `tomcat_splash` function and adjusting the custom settings in `tomcat_config` and `tomcat_update`.

**Note** Though this utility was only committed to GitHub in August 2021, it has been used in production since 2012 and has been
tested with various implementations of Tomcat and TomEE since Tomcat 6.0.29.

## Installation

The repository structure should be kept as is; but can be located anywhere. By convention, we place it in `/opt/tomcat-cli`:

```
cd /opt; sudo git clone https://github.com/ISLECode/tomcat-cli
```

Then simply make a symbolic link to the `bin/tomcat` executable script into a PATH-aware directory, such as `/usr/local/bin`:

```
cd /usr/local/bin; ln -s /opt/tomcat-cli/bin/tomcat .
```

## Documentation

The utility offers an extensive embarked `man(1)`-page which can be accessed as `tomcat --man` or `tomcat COMMAND --man` where
COMMAND is a support command.

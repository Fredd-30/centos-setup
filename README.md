# Post-installation setup script for CentOS 7 servers

(c) Niki Kovacs 2019 

This repository provides an "automagic" post-installation setup script for
servers running CentOS 7.

# Quick & Dirty

Perform the following steps.

  1. Install a minimal CentOS 7 system.

  2. Create a non-root user with administrator privileges.

  3. Install Git: `sudo yum install git`

  4. Grab the script: `git clone https://github.com/kikinovak/centos-setup`

  5. Change into the new directory: `cd centos-setup`

  6. Run the script: `sudo ./centos-7-setup.sh --setup`

  7. Grab a cup of coffee while the script does all the work.

  8. Reboot.

# Customizing a CentOS server

Turning a minimal CentOS installation into a functional server always boils
down to a series of more or less time-consuming operations. Your mileage may
vary of course, but here's what I usually do on a fresh CentOS installation:

  * Customize the Bash shell: prompt, aliases, etc.

  * Customize the Vim editor.

  * Setup official and third-party repositories.

  * Install a complete set of command line tools.

  * Remove a handful of unneeded packages.

  * Enable the admin user to access system logs.

  * Disable IPv6 and reconfigure some services accordingly.
  
  * Configure a persistent password for sudo.

  * Etc.

The `centos-7-setup.sh` script performs all of these operations.

Configure Bash and Vim and set a more readable default console resolution:

# ./centos-7-setup.sh --shell

Setup official and third-party repositories:

# ./centos-7-setup.sh --repos

Install the Core and Base package groups along with some extra tools:

# ./centos-7-setup.sh --extra

Remove a handful of unneeded packages:

# ./centos-7-setup.sh --prune

Enable the admin user to access system logs:

# ./centos-7-setup.sh --logs

Disable IPv6 and reconfigure basic services accordingly:

# ./centos-7-setup.sh --ipv4

Configure password persistence for sudo:

# ./centos-7-setup.sh --sudo

Perform all of the above in one go:

# ./centos-7-setup.sh --setup

Enable packet forwarding:

# ./centos-7-setup.sh --nat

Strip packages and revert back to an enhanced base system:

# ./centos-7-setup.sh --strip

Display help message:

# ./centos-7-setup.sh --help

If you want to know what exactly goes on under the hood, open a second terminal
and view the logs:
```
$ tail -f /tmp/centos-7-setup.log
```


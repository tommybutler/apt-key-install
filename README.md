# apt-key-install
Automatically retrieve and register a given repository's PGP key with apt

# Synopsis
  `apt-key-install 5C808C2B65558117`

  `apt-keyt-install 5C808C2B65558117 keyserver.ubuntu.com`

# Usage
When you run `apt-get update` and you get an error like the one below, use
this script to fix the issue now and any time it happens in the future.

  `"The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 5C808C2B65558117"`

The reason you saw the error above is because you (or a program) added a new
repository to /etc/apt/sources.list or /etc/apt/sources.list.d/
and the apt package management system doesn't yet recognize and trust the
encryption key that was used to sign the packages in the that repository.

# Installation
As root (or with sudo), copy the apt-key-install file to /usr/local/sbin and
make it executable:
`chmod u+x /usr/local/sbin/apt-key-install`

If you'd rather not install the script, you can still get (less-robust but)
similar results by copying the contents of the "apt-key-install-bashrc" file
into your .bashrc file and sourcing it.

# Notes
* Be aware that you need root privileges to run this script (because it calls
  commands that require root access)
* The script wants to run as bash code, but is written in portable POSIX shell
  and should work on any Debian or Debian-derivative distribution
  (Ubuntu, Mint, etc)

# SECURITY WARNING
MAKE SURE YOU TRUST THE KEY(S) YOU REGISTER WITH THIS TOOL!

# Copyright
Tommy Butler, 2015

# License
GNU GPL version 3 or higher

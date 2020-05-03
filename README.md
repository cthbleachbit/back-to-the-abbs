back-to-the-abbs
================

Neta from "back to the future", a repository of AOSC OS build configurations that I don't think suitable in main AOSC abbs tree, mostly for the following reasons:
 - radical patches
 - non-free and non-redistributable binaries
 - shabby utilities written by myself with no safety/appropriateness guarantees (lul)
 - experimental and/or dirty hacks

~I will not provide binary archives for packages here, nor users should redistribute copyright restricted packages build from these configurations.~ A subset of packages targeting three current AOSC OS release streams (stable, testing) are hosted on [my static file host](https://static.cth451.me/btta) as apt sources. Due to copyright restrictions, some packages won't be available in the repository for direct download. For instructions on how to build these packages for yourself, check AOSC cadet training on [main tree wiki](https://github.com/AOSC-Dev/aosc-os-abbs/wiki).

Packages here might move to the main ABBS tree if the situation allows, including but not limited to:

* change of upstream licence regarding redistribution,
* software out of beta releasing on time (GLaDOS: ?),
* upstream fix rendering hacks obsolete.

A list of packages moved from here to the main tree will be available at `MOVED.md`.

Adding apt sources
------------------

##### 1A For users on the stable branch

Download [this deb](https://static.cth451.me/btta/deploy.deb), and install.

##### Or... 1B Manual setup for custom branches

AOSC OS stores apt repo information in a similar way as may other distros in `/etc/apt`. To add `btta` to your system, create a new text file `btta.list` under `/etc/apt/sources.list.d` with following contents (replace `$STREAM` with the release stream you are currently on, e.g. `stable`, `testing` or `explosive`):

```
# cth451's back-to-the-abbs repo
deb https://static.cth451.me/btta $STREAM main
```

Ask `apt-key` to trust the signing key of btta with the following command. This public key should carry a signature from my main GPG key.

```
curl https://static.cth451.me/btta/pubkey/btta.pub | apt-key --keyring /etc/apt/trusted.gpg.d/btta.gpg add -
```

##### 2 Profit

Ask apt to refresh itself by `apt update`, and you should be able to install from btta.

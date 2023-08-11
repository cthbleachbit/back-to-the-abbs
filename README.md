back-to-the-abbs
================

Neta from "back to the future", a repository of AOSC OS build configurations that I don't think suitable in main AOSC abbs tree, mostly for the following reasons:
 - radical patches
 - non-free and non-redistributable binaries
 - shabby utilities written by myself with no safety/appropriateness guarantees (lul)
 - experimental and/or dirty hacks

~I will not provide binary archives for packages here, nor users should redistribute copyright restricted packages build from these configurations.~ A subset of redistributable packages current AOSC OS stable release stream are available as apt binary sources. Due to copyright restrictions, some packages won't be available in the repository for direct download. For instructions on how to build these packages for yourself, check AOSC cadet training on [main tree wiki](https://github.com/AOSC-Dev/aosc-os-abbs/wiki).

Packages here might move to the main ABBS tree if the situation allows, including but not limited to:

* change of upstream licence regarding redistribution,
* software out of beta releasing on time (GLaDOS: ?),
* upstream fix rendering hacks obsolete.

A list of packages moved from here to the main tree will be available at `MOVED.md`.

Adding apt sources
------------------

##### 1A For users on the stable branch

Download [this deb](https://btta.cth451.me/deploy.deb), and install.

##### Or... 1B Manual setup for custom branches

AOSC OS stores apt repo information in a similar way as may other distros in `/etc/apt`. To add `btta` to your system, create a new text file `btta.list` under `/etc/apt/sources.list.d` with following contents.

```
deb [signed-by=/etc/apt/trusted.gpg.d/btta.gpg] https://btta.cth451.me stable main
```

Download repo signing key from https://github.com/cthbleachbit/back-to-the-abbs/raw/master/btta-bases/btta/autobuild/overrides/etc/apt/trusted.gpg.d/btta.gpg and place it in `/etc/apt/trusted.gpg.d`.

##### 2 Profit

Ask apt to refresh itself by `apt update`, and you should be able to install from btta.

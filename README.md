aur-activitywatch-bin
=====================

[![aur](https://img.shields.io/aur/version/activitywatch-bin)](https://aur.archlinux.org/packages/activitywatch-bin)
[![Autoupdate](https://github.com/ActivityWatch/aur-activitywatch-bin/actions/workflows/autoupdate.yml/badge.svg)](https://github.com/ActivityWatch/aur-activitywatch-bin/actions/workflows/autoupdate.yml) (WIP, not actually autoupdating yet)

An AUR package for ActivityWatch using prebuilt binaries.


## How to update the AUR package

You need:
 - Maintainer rights to the AUR package
 - Your AUR ssh key configured

After checking that the package builds correctly (using `make package`) simply run:

```sh
make srcinfo
git add srcinfo
git commit -m "Updated .SRCINFO"
git remote add aur aur@aur.archlinux.org/activitywatch-bin.git
git push aur
```

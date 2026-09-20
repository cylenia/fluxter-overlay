# UNMAINTAINED!!!

I use the official desktop client now. I also maintain [an overlay](https://git.cylenia.dev/cylenia/fluxer-overlay) for that if you are interested.
Feel free to fork and continue updating this overlay! If you end up doing that, email me or message me on Fluxer and I will add your fork to this readme.
Those details are on my website.

# fluxter-overlay

Gentoo overlay for [polonius' fluxer-tui fork called fluxter](https://github.com/AIVirtuoso/fluxter).\
Note that unlike the original project which was MIT, this fork is GPL-3+.\
This overlay is still MIT.

## Installation

It is mandatory to use the live ebuild at the current moment, because no releases exist.\
You will need to set `/etc/portage/package.accept_keywords/fluxter` to `=net-im/fluxter-9999 **`.\
Replace all "doas" with "sudo" if you use sudo.

```
# if you don't already have eselect-repository install it:
doas emerge --ask app-eselect/eselect-repository
# add the repository:
doas eselect repository add fluxter-overlay git https://github.com/cylenia/fluxter-overlay
# sync your repositories:
doas emerge --sync
# install fluxer-tui:
doas emerge --ask net-im/fluxter
```

## Migration Guide

If you used this overlay before 09/10/26, you may have the old package name.\
Polonius changed the name of the package and repo upstream to Fluxter.\
This requires manual effort to adjust.\
Replace all "doas" with "sudo" if you use sudo.

```
# remove the old name
doas eselect repository remove -f fluxer-tui-overlay
# unmerge the old package
doas emerge --unmerge net-im/fluxer-tui
# if you were using the live ebuild, delete old accept_keywords
doas rm /etc/portage/package.accept_keywords/fluxer-tui
# follow installation steps above
```

## Credits

- polonius for maintaining the fork of fluxer-tui
- dogbonewish for creating the original project
- myn for helping me with this overlay

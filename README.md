# Plymouth for openrc

## This contains multiple openrc scripts to start plymouth and boot into the display manager of your choice

### Dependencies

- The display manager that the file is named after

- Plymouth

- OpenRC

### Preparation

Add the following:

```
# in /etc/default/grub
GRUB_CMDLINE_LINUX_DEFAULT="... quiet splash" # Replace ... with whatever is already there by default
```

```
# in /etc/mkinitcpio.conf
HOOKS=(... plymouth ...)  # Replace ... with whatever you already have
```
Issue the following in a terminal

`doas grub-mkconfig -o /boot/grub/grub.cfg # use sudo if you don't have doas`

`doas mkinitcpio -P # use sudo if you don't have doas`

### Goals

It is unclear what to do with each file currently. I forked this so I could add the ly script. I will add better documentation in the future

## Note for ly

This guy is way easy. Just enter the following commands, and it should work fine.

```
doas cp ly /etc/init.d/ # use sudo if you don't have doas

doas rc-update add ly default # use sudo if you don't have doas
```

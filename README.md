![Image: Example of this fork with basic config and two urxvt windows](https://i.imgur.com/B4glsnQ.png)

# Huh what is this?

This is quick and dirty attempt to patch double border into i3-gaps.

Double border is calculated as half of border width, eg. consider this
part of config:

```
for_window [class="^.*"] border pixel 16

client.background  #121b27
```

all windows will have 8px actual border and outer 8px will be filled with
background color.

As you might caught on, this leaves no ability to have old "one border" look
with this fork. This why I call it quick and dirty :)

# Installation
```bash
cd /path/where/you/want/the/repository

# clone the repository
git clone https://www.github.com/max-lv/i3 i3-gaps
cd i3-gaps

# compile & install
autoreconf --force --install
rm -rf build/
mkdir -p build && cd build/

# Disabling sanitizers is important for release versions!
# The prefix and sysconfdir are, obviously, dependent on the distribution.
../configure --prefix=/usr --sysconfdir=/etc --disable-sanitizers
make
sudo make install
```
## Arch Aur Package
https://aur.archlinux.org/packages/i3-gaps-doubleborder/
```
yay -S i3-gaps-doubleborder
```

# Dependancies
* libdev
* libxkbcommon-x11
* pango
* perl
* startup-notification
* xcb-util-cursor
* xcb-util-keysyms
* xcb-util-wm
* xcb-util-xrm
* yajl
* asciidoc (make)
* bison (make)
* flex (make)
* xmlto (make)

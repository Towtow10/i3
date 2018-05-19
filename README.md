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
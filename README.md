# nice-view-mod
Fork of [GPeye's nice-view-repo](https://github.com/GPeye/nice-view-mod)

![example](/assets/trunks.gif)

For a complete example of forking and editing this repo to make a custom nice_view shield with custom animations, check out [https://github.com/GPeye/urchin-peripheral-animation](https://github.com/GPeye/urchin-peripheral-animation)


SOFLE58 users read:

- fork [this repo](https://github.com/a741725193/zmk-sofle)
- clone code
- change your keymap as need


## Usage

To use this module, first add it to your config/west.yml by adding a new entry to remotes and projects:

```yml
manifest:
  remotes:
      # zmk official
    - name: zmkfirmware
      url-base: https://github.com/zmkfirmware
    - name: JimmyBlackley                         #new entry
      url-base: https://github.com/JimmyBlackley  #new entry
  projects:
    - name: zmk
      remote: zmkfirmware
      revision: main
      import: app/west.yml
    - name: nice-view-dbz                 #new entry
      remote: JimmyBlackley               #new entry
      revision: main                      #new entry
  self:
    path: config
```
simply swap out the default yaml path for this one to get trunks on your kb.


## TODO:

- Add dithering
- Work on automating pipeline of Video -> B/W -> 1bit with dither -> png frames -> rotate and LVGL 1bit color
- Make tool to automatically add all the individual LVGL frames to the art.c
- Add more branches to this repo with more animations
- Test limits of how many frames can be added, and animation fps before keyboard breaks (I am using a nice-nano v1)



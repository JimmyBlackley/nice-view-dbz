# nice-view-mod
Fork but adding a small DBZ Trunks aniamtion

[Other Examples](https://github.com/duckyb/zmk-urchin) with build actions set up to build your firmware with github actions and is of course meant for boards with the nice!view. P

![example](/assets/trunks.gif)

For a complete example of forking and editing this repo to make a custom nice_view shield with custom animations, check out [https://github.com/GPeye/urchin-peripheral-animation](https://github.com/GPeye/urchin-peripheral-animation)

## TODO:

- Add dithering
- Work on automating pipeline of Video -> B/W -> 1bit with dither -> png frames -> rotate and LVGL 1bit color
- Make tool to automatically add all the individual LVGL frames to the art.c
- Add more branches to this repo with more animations
- Test limits of how many frames can be added before keyboard breaks (I am using a nice-nano v1)


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
simply swap out the default nice_view shield on the board for the custom one in your build.yaml file.

Sofle58 users just change the right board, since the left board usually is used for status info
```yml
---
include:
  - board: nice_nano_v2
    shield: urchin_left nice_view_adapter  nice_view_custom #custom shield
  - board: nice_nano_v2
    shield: urchin_right nice_view_adapter nice_view_custom #custom shield
```

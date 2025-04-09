# Marlin for Makerselect v2 / Wanhao Duplicator i3

This is a relatively modern version of the Marlin printer firmware, customized
for the Monoprice Makerselect v2 / Wanhao Duplicator i3 printer.

By modern standards, these printers don't have a lot of flash, so fitting new
features is difficult. I've managed to hack and slash until there was room to
add

- All the bugfixes from the `bugfix-2.0.x` branch,
- BLTouch support for automatic Z homing, and
- Bilinear bed leveling and correction.

I've also tuned the basic machine properties to match the behavior of my
printer.

I haven't gotten the 2.1.x branch to fit. You might be able to pull it off if
you remove BLTouch support.

## Building

You will need `platformio`. I can't figure out how to enable the appropriate
optimizations in the Arduino IDE.

With `platformio` installed, the key is:

```
platformio run -e sanguino1284p_optimized
```

...where the `_optimized` bit selects an alternate version of the Sanguino
environment with more aggressive compiler optimizations. (I didn't create this,
it was there all along.)

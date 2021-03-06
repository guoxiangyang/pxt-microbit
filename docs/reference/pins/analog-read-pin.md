# Analog Read Pin

Read an **analog** signal (`0` through `1023`) from the
[pin](/device/pins) you say.

```sig
pins.analogReadPin(AnalogPin.P0)
```

### Parameters

* a [string](/reference/types/string) that stores the name of the pin
  you say (`P0` through `P4`, or `P10`)

### Returns

* a [number](/reference/types/number) from `0` through `1023`

This program reads pin `P1` and shows the number
on the LED screen.

```blocks
basic.forever(() => {
    let value = pins.analogReadPin(AnalogPin.P1)
    basic.showNumber(value)
});
```

### See also

[micro:bit pins](/device/pins),
[on pin pressed](/reference/input/on-pin-pressed),
[analog write pin](/reference/pins/analog-write-pin),
[digital read pin](/reference/pins/digital-read-pin),
[digital write pin](/reference/pins/digital-write-pin)

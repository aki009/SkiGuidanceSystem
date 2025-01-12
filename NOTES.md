# Implementation Notes

## Master Controller

### SoC

It seems ESP32-S3 fits the bill here. It has enough processing power for voice recognition. This means a prototype system candidate is something like the M5Stack CoreS3 SE.

**RESEARCH**

- Test recognition speed
- External microphone input (the CoreS3 has built-in mics, but no external microphone input)

## Remote Units

### SoC

If the master is a M5Stack unit, then a M5StickC might be the way to go, with an external vibrator.

**RESEARCH**

- Test battery endurance of the built-in M5StickC while powering an external vibrator


## Wireless Link

If the M5Stack is used as a prototype, the Bluetooth features built into ESP32 are the obvious solution.

Perhaps use the Bluetooth serial module.

The master maintains connections with both remotes and propagates error conditions if needed.

Consider a 100ms ping to make sure a bad link is detected quickly.


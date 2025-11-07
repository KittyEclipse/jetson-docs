# Fan Control

By default, the Jetson Nano *should* utilize the fan whenever the device gets too hot.

However, if you wish to control the fan manually, you may run the following command:

```
echo ${FAN_SPEED} | sudo tee /sys/devices/pwm-fan/target_pwm
```

`FAN_SPEED` must be an integer value ranging from `0` to `255` (inclusive).

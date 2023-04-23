# dactyl zmk-config

### How it works

2 keyboard keyboard part connect via bluetooth to a dongle. Dongle connects to computer via USB, but it can switch to different device via bluetooth.

### How to build

From `app` directory in zmk repo run:
```
west build -b nice_nano_v2 -d build/right -- -DZMK_CONFIG=$(pwd)/../../zmk-config/config -DSHIELD=dactyl_right
west build -b nice_nano_v2 -d build/left -- -DZMK_CONFIG=$(pwd)/../../zmk-config/config -DSHIELD=dactyl_left
west build -b nice_nano_v2 -d build/dongle -- -DZMK_CONFIG=$(pwd)/../../zmk-config/config -DSHIELD=dactyl_dongle
```

Above command assumes that zmk repo and this one is in the same directory.
Instruction to setup zmk repo:
 - Follow steps from https://zmk.dev/docs/development/setup
 - Install zephyr SDK with `yay -S zephyr`

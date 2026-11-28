# PR #544 test firmware

Target: **Keychron V3 Max ANSI encoder (knob), STM32F401 / STM32 DFU only**.

Source: https://github.com/Keychron/qmk_firmware/pull/544

Source commit: `56527d219ccb7450505b371cbdff7d0cc5f1fcd0` (base branch: `2025q3`).

Built with ARM GCC 15.2.0 using:

```sh
make keychron/v3_max/ansi_encoder:default
make keychron/v3_max/ansi_encoder:keychron
```

The `.bin` files are firmware images for flashing through STM32 DFU. Choose the
file matching the desired keymap; do not flash both. These are not firmware for
ISO/JIS, non-knob models, other V Max keyboards, or radio-module updates.

Both builds passed without compiler warnings. The focused wireless suite passed
19 tests with adaptive NKRO and 21 with classic NKRO. This revision has not been
tested on hardware. It addresses dropped reports during reconnect; the reported
Command/Option symptom is not confirmed fixed.

`SHA256SUMS` contains SHA-256 checksums of both firmware images. Keep the official
firmware for this exact keyboard available for rollback before testing.

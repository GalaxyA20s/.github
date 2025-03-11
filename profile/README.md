# Galaxy A20s Overview

## Booting into special modes
* **Recovery:**
    * `adb reboot recovery`
    * With the phone off, press and hold `Volume Up` + `Power`. This is quite tricky since sometimes it doesn't work and the phone ends up booting Android normally.
* **Download Mode (with bootloader lock & unlock options):** With the phone off, hold both volume keys & plug the phone to a computer.
* **Download Mode (only download):** `adb reboot-bootloader`

Additionally, the phone can always be forced to reboot by holding `Volume Down` + `Power` for some seconds.

## Unlocking the bootloader
The process is pretty much the same as in any other Samsung phone. Remember that this will perform a factory reset.
1. Make sure your phone has internet connection
2. Enable developer options and turn on OEM unlocking.
3. Shut down the phone & boot into download mode
4. Unlock the bootloader by holding `Volume Up` to access the unlock menu & then confirm the action with `Volume Up`.

## Flashing
You can use Odin (Windows) or Heimdall (Windows/Linux).

Before flashing any partition, it's suggested to first flash an **empty vbmeta image**. If you don't, the bootloader may refuse to boot the device.

### Boot/Recovery
Due to a bug in the bootloader, recovery and boot images need to be "fixed" before being flashed, otherwise the phone will refuse to boot them with a **"SECURE CHECK FAIL"** error. More info in [this repository](https://github.com/GalaxyA20s/A20s-Fix-Bootable-Image).

[TWRP](https://twrp.me/samsung/samsunggalaxya20s.html) is available for this device but there are some things you must know:
* If you are on the stock firmware (OneUI), the recovery is replaced by the stock one on each boot, making it hard to actually boot into TWRP.
* It's not able to access the internal storage nor anything in `/data` unless you disable encryption.

### GSIs
More information can be found on [TrebleDroid's Wiki](https://github.com/TrebleDroid/treble_experimentations/wiki/Samsung-Galaxy-A20s).

## Additional Resources
- [XDA Developers Forum](https://xdaforums.com/c/samsung-galaxy-a20.9753/) -Most threads are for the Exynos Galaxy A20, there's not much stuff for the A20s
- [A20s Telegram Group](https://t.me/SamsungGalaxyA20s) -Here you can find more step-by-step instructions and get help from other users

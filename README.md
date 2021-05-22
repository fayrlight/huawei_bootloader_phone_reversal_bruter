# unlock Huawei bootloader

## TODO
Use sysreq to emulate or inject volume down & power button press for 200,000 trys, the vendor likely made this Huawei intentionally

```
8f8ddef8 68 46 76 8f     addr       s_reboot-bootloader_8f764668                     = "reboot-bootloader"
8f8ddefc 7c 46 76 8f     addr       s_getvar:_8f76467c                               = "getvar:"
8f8ddf00 84 46 76 8f     addr       s_download:_8f764684                             = "download:"
8f8ddf04 90 46 76 8f     addr       s_oem_getlog_8f764690                            = "oem getlog"
8f8ddf08 9c 46 76 8f     addr       s_flashing_lock_critical_8f76469c                = "flashing lock_critical"
8f8ddf0c 9c 46 76 8f     addr       s_flashing_lock_critical_8f76469c                = "flashing lock_critical"
8f8ddf10 b4 46 76 8f     addr       s_flashing_unlock_critical_8f7646b4              = "flashing unlock_critical"
8f8ddf14 d0 46 76 8f     addr       s_flashing_get_unlock_ability_8f7646d0           = "flashing get_unlock_ability"
8f8ddf18 ec 46 76 8f     addr       s_oem_device-info_8f7646ec                       = "oem device-info"
8f8ddf1c fc 46 76 8f     addr       s_preflash_8f7646fc                              = "preflash"
8f8ddf20 08 47 76 8f     addr       s_oem_enable-charger-screen_8f764708             = "oem enable-charger-screen"
8f8ddf24 24 47 76 8f     addr       s_oem_disable-charger-screen_8f764724            = "oem disable-charger-screen"
8f8ddf28 40 47 76 8f     addr       s_oem_off-mode-charge_8f764740                   = "oem off-mode-charge"
8f8ddf2c 54 47 76 8f     addr       s_oem_select-display-panel_8f764754              = "oem select-display-panel"
8f8ddf30 70 47 76 8f     addr       s_oem_uart_enable_8f764770                       = "oem uart enable"
8f8ddf34 80 47 76 8f     addr       s_oem_uart_disable_8f764780                      = "oem uart disable"
8f8ddf38 94 47 76 8f     addr       s_oem_sysrq_enable_8f764794                      = "oem sysrq enable"
8f8ddf3c a8 47 76 8f     addr       s_oem_sysrq_disable_8f7647a8                     = "oem sysrq disable"
8f8ddf40 bc 47 76 8f     addr       s_oem_ramdump_enable_8f7647bc                    = "oem ramdump enable"
8f8ddf44 d0 47 76 8f     addr       s_oem_ramdump_disable_8f7647d0                   = "oem ramdump disable"
8f8ddf48 e4 47 76 8f     addr       s_oem_kmemleak_enable_8f7647e4                   = "oem kmemleak enable"
8f8ddf4c f8 47 76 8f     addr       s_oem_kmemleak_disable_8f7647f8                  = "oem kmemleak disable"
8f8ddf50 10 48 76 8f     addr       s_oem_sendkernel_8f764810                        = "oem sendkernel"
8f8ddf54 20 48 76 8f     addr       s_flash:rescue_recovery_8f764820                 = "flash:rescue_recovery"
8f8ddf58 38 48 76 8f     addr       s_oem_getversion_8f764838                        = "oem getversion"
8f8ddf5c 48 48 76 8f     addr       s_oem_hwdog_certify_begin_8f764848               = "oem hwdog certify begin"
8f8ddf60 60 48 76 8f     addr       s_flash:slock_8f764860                           = "flash:slock"
8f8ddf64 6c 48 76 8f     addr       s_oem_hwdog_certify_close_8f76486c               = "oem hwdog certify close"
8f8ddf68 34 40 76 8f     addr       s_flashing_unlock_8f764034                       = "flashing unlock"
8f8ddf6c 84 48 76 8f     addr       s_flashing_lock_8f764884                         = "flashing lock"
8f8ddf70 28 40 76 8f     addr       s_oem_unlock_8f764028                            = "oem unlock"
8f8ddf74 94 48 76 8f     addr       s_oem_relock_8f764894                            = "oem relock"
8f8ddf78 a0 48 76 8f     addr       s_oem_get-bootinfo_8f7648a0                      = "oem get-bootinfo"
8f8ddf7c b4 48 76 8f     addr       s_oem_lock-state_info_8f7648b4                   = "oem lock-state info"
8f8ddf80 c8 48 76 8f     addr       s_oem_check-rootinfo_8f7648c8                    = "oem check-rootinfo"
8f8ddf84 dc 48 76 8f     addr       s_oem_frp-unlock_8f7648dc                        = "oem frp-unlock"
8f8ddf88 ec 48 76 8f     addr       s_oem_ddr-test_8f7648ec                          = "oem ddr-test"
8f8ddf8c fc 48 76 8f     addr       s_oem_get-psid_8f7648fc                          = "oem get-psid"
8f8ddf90 0c 49 76 8f     addr       s_oem_get_hwnff_ver_8f76490c                     = "oem get_hwnff_ver"
8f8ddf94 20 49 76 8f     addr       s_oem_get-product-model_8f764920                 = "oem get-product-model"
8f8ddf98 38 49 76 8f     addr       s_oem_oeminforead-ANDROID_VERSION_8f764938       = "oem oeminforead-ANDROID_VERSI
8f8ddf9c 58 49 76 8f     addr       s_oem_oeminforead-SYSTEM_VERSION_8f764958        = "oem oeminforead-SYSTEM_VERSION"
8f8ddfa0 78 49 76 8f     addr       s_oem_oeminforead-hotainfo_8f764978              = "oem oeminforead-hotainfo"
8f8ddfa4 94 49 76 8f     addr       s_oem_get-build-number_8f764994                  = "oem get-build-number"
8f8ddfa8 ac 49 76 8f     addr       s_oem_battery_present_check_8f7649ac             = "oem battery_present_check"
8f8ddfac c8 49 76 8f     addr       s_oem_get_key_version_8f7649c8                   = "oem get_key_version"
8f8ddfb0 dc 49 76 8f     addr       s_oem_get_bootFail_ver_8f7649dc                  = "oem get_bootFail_ver"
8f8ddfb4 f4 49 76 8f     addr       s_oem_reboot_boot_dump_8f7649f4                  = "oem reboot_boot_dump"
8f8ddfb8 0c 4a 76 8f     addr       s_oem_get_bootFail_info_8f764a0c                 = "oem get_bootFail_info"
```

## Summary

After closing the official EMUI website, which allowed you to retrieve the code to unlock the bootloader of Huawei/Honor phones, here is a python script to retrieve it by yourself.

It uses a bruteforce method, based on the Luhn algorithm and the IMEI identifier used by the manufacturer to generate the unlocking code.

The original version was developed by [SkyEmi](https://github.com/SkyEmie). I made some tweaks for saving failed attempts to file, because brutforcing is taking a **looooooong** time. I'm trying to hack my P20 Pro with this. Because Huawei placed another obstacle in th way, as you have 5 attempts for inserting the unlook key, than your phone will restart automatically. So I have to reboot in fastboot mode every 4 attempts. This increases the amount of time while trying, but couldn't find a better solution. 

## Instructions

### Connecting a device in ADB mode

1. Enable developer options in Android at your phone.

    * Go to Settings > System > About device > tap _Build number_ seven times to enable developer options.

2. Enable USB debugging in Android.

    * Go to Settings > System > Developer options and enable USB debugging.

3. Connect your device to the computer 

4. ``` 
    git clone https://github.com/haexhub/huaweiBootloaderHack.git
    cd huaweiBootloaderHack
    python3 unlock.py <IMEI>
    ```
4. Make a few cups of coffee or tea => sleep => repeat :D

## FAQ & Troubleshooting

**The application doesn't work. Is there anything I should have installed?**

Yes, it was developed with python3 so you'll need it. You can install the latest version from [here](https://www.python.org/downloads/).
You also need [adb](https://www.xda-developers.com/install-adb-windows-macos-linux/) installed
as well as [fastboot](https://www.droidwiki.org/wiki/Fastboot_(Tool))

# sh1ttyexec
Exploit allowing for code execution on keyrolled chromebooks with kernel version 6.

</br>Guide written by Lxrd, copied from the crosbreaker discord, and reformatted for GitHub. [message link](https://discord.com/channels/1375357349425971231/1437920169224831038/1437920169224831038)

## if you need any support join [the discord](https://discord.gg/92gCC4Whu4)

1. Powerwash the device
2. Start enrolling the device then open powerwash menu (ctrl+alt+shift+r) on Enrollmet screen not the please wait and wait till it crashes back to OOBE
3. Try enrolling again but the moment enrollment starts (the screen that says enrollment, not please wait) esc+refresh+power ( its timing sensitive so don’t expect to get it first try), and you are done, block_devmode is set to 0 and you can do bad reco unverified which can help facilitate exploits/unenrollments like quicksilver on keyrolled devices (kv6). To enter an unverified recovery image, esc+refresh+power then ctrl+d and enter, esc+refresh+power again and plug in usb.

Long explanation:</br>
This is due to the fact that when you enroll you go through state determination and if you crash back to oobe and try to enroll again, state determination happens a second time. As a result, it tries to clear fwmp but it can’t because the tpm is locked, however it does set block_devmode in vpd to 0. Shortly after, it sets it back to 1 but we can simply restart or enter recovery menu before it is able to. This allows us to boot unverified recovery images and gain/lead to code execution via badrecovery unverified. A project called recomm3r is being released by carbon soon which is an unverified recovery image that has a clean GUI and many utilities like sh1mmer.

</br>**This was patched in v143**

</br>Vid tut:</br>
https://drive.google.com/file/d/1Z4Lv82w_QGy-TTdSvdMAu0gf8NOJyKfx/view
</br></br>
Credits:
</br>Lxrd for finding the vulnerability
</br>Crosbreaker/Wininit, testing
</br>Wininit, Video
</br>Olyb, badrecovery unverified.
</br>Con, having aura
</br>Carbon, Scottie, and DMD, recomm3r
</br>Crossjbly/xz8f, finding that the powerwash keybind allows us to crash back to oobe more easily/effectively.

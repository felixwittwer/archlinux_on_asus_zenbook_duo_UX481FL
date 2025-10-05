# custom keys info

If you are courius this file explains some stuff behind the two custom keys e.g. what the keycodes are and how to get them.

Run `sudo dmesg -w`. This should return something like this when the keys are pressed:

```
[] asus_wmi: Unknown key code 0x9c
[] asus_wmi: Unknown key code 0x6a
```

> [!NOTE]
> Inside [ ] will be a timecode.

`0x9c` will be the key that swaps all windows from both screent to oneanother.  
`0x6a` will be the key for disabling the ScreanPad+ originally there were three modes behind this key. On, Off and black (disabled but not disconnected/shutoff)
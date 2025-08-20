# Update BIOS

> [!CAUTION]
> Updation your BIOS is at your own risk! If not done properly you could render your laptop unusable! <br>
> Double check that you download the correct BIOS image! There is a difference between UX481FL and UX481FLY. There is als a UX481FA version. The sticker on the underside of the laptop only tells you the rough model (UX481F).

> [!TIP]
> To check which version of laptop you have turn the laptop on and enter BIOS with `F2`. Go to the `Advanced` tab and then down to  `ASUS ES Flash 3 Utility`. The complete model/platform will be shown on the right side under **_Platform:_** of the current BIOS. Exit by pressing Esc.

## Updating the BIOS

### Requirements
- a USB flash drive ideally completly empty
- a machine where cou can download the BIOS image and copy it to the drive
- your Asus ZenBook Duo

### Step 1 

Download the newest BIOS image (308) for the offical ASUS website.

> [!WARNING]
> Check your exact model number again and download the right BIOS image. If you don't know the exact model number read the TIP section above.

> https://www.asus.com/laptops/for-home/zenbook/zenbook-duo-ux481/helpdesk_bios/?model2Name=Zenbook-Duo-UX481

Extract the ZIP file you got and copy the file `UX481FLAS.308` onto the USB flash drive.

### Step 2

Turn on your ZenBook Duo and enter BIOS with `F2`. Go to the `Advanced` tab and then down to  `ASUS ES Flash 3 Utility`. Open **_ASUSTeK Easy Flash Utility_** by pressing enter.

> [!CAUTION]
> Now the critical part starts. Don't soley rely on this guide and its instructions. Have a look at ASUSes official guides.

Inside **_ASUSTeK Easy Flash Utility_** on the left side you can switch to your flash drive. There should be something like FS0 and FS1. FS1 is likely your USB drive. Select it with the up and down arrow keys.

> [!CAUTION]
> With the next step you will be installing the new BIOS. Do not under any circumstances disconnect power or inerrupt the process of the BIOS update! This could render your device unusable!

Press the right arrow key to select the `UX481FLAS.308` and press enter.

The new BIOS version should now be installed.

# Arch installation

This file contains full instructions for how to install Arch linux via the `archinstall` command on the ZenBook Duo.

## Prerequisites

### BIOS Version 308

The newest BIOS Version for the **_Asus ZenBook UX481FL_** is version **_308_**[^1]. This guide is based on that version and with all the issues I had before it is probably a smart move to update to the newset version.

> [!NOTE]
> BIOS Image can be found here <br>
> https://www.asus.com/laptops/for-home/zenbook/zenbook-duo-ux481/helpdesk_bios/?model2Name=Zenbook-Duo-UX481 

Detailed instructions on updating the BIOS can be found in [update_bios.md](update_bios.md)

### BIOS Settings

- under the `Advanced` tab go down to `SATA Configuration` an set `SATA Mode Selection` to `[AHCI]`
- under the `Boot` tab go to `Fast Boot` and disable it
- under the `Security` tab go down to `Secure Boot` and set it to `Disabled`
- press `F10` to save and exit BIOS

You have now set the SATA mode to AHCI, disabled Fast Boot and Secure Boot.

### SSD Firmware

I am using a **_Samsung 970 EVO Plus 1TB_** make sure it als has the newest version installed. The eseaiest way to check is by using Samsung Magican on a Windows machine.

[^1]: https://www.asus.com/laptops/for-home/zenbook/zenbook-duo-ux481/helpdesk_bios/?model2Name=Zenbook-Duo-UX481
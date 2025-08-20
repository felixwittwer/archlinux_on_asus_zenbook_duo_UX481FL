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

## Booting

When powering on your ZenBook Duo you should se a screen similar to this one. Ther will be a 15 second timer at the bottom just press the down and up arrow keys to abort the timer. 

![standard grub screen](assets/arch_installation/grub_boot.png)

With the first option selected press `e`. We will input some additional starting parameters.

> [!NOTE]
> **Why are we adding additional parameters?** <br>
> As I noticed this exact laptop model has difficulties having the SSD in a D0 state where it can be used to write the installation on. If you don't use these parameters the SSD will likely show up in the beginning (`lsblk`) but afterwards turn into a D3cold state to save power. I suppose this is happening because the installer and Laptop dont communicate correctly. By inputting these parameters the SSD will remain in the D0 state no matter what.

![grub screen after e pressed](assets/arch_installation/grub_boot_e.png)

Now please add these parameters to the line right after the parameters you already see. 

`nvme_core.default_ps_max_latency_us=0 pcie_aspm=off pcie_port_pm=off nvme.noacpi=1`

![grub input parameters](assets/arch_installation/grub_boot_e_parameters.png)

> [!NOTE]
> **What do the parameters do?** <br>
> - **_default_ps_max_latency_us=0_** → disables APST (auto power states). <br>
> - **_pcie_aspm=off_** → disables PCIe Active State PM. <br>
> - **_pcie_port_pm=off_** → disables port-level runtime PM (stops link from going to D3cold). <br>
> - **_nvme.noacpi=1_** → ignores buggy ACPI tables that might try to override.

![arch start](assets/arch_installation/arch_start.png)

Before starting the installation we need to perform one last step to stop the SSD from going into a power save mode. 
Execute the following command:

``` shell
cat /sys/class/nvme/nvme0/device/power/control
```

If it returnes `auto` (which is likely) execute:

``` shell
echo on | sudo tee /sys/class/nvme/nvme0/device/power/control
```

> [!NOTE]
> You can check if your SSD is working by running `lsblk`. Under the nvme section you should se a `nvme0n1`. Make srue the size is correct so however large your SSD is if the SSD is in a poersaving mode and the installation can't access it there will be a size of 0B.

## Installation

### Connect to the Internet

First make sure you have a stable internet connection or a internet conenction at all. Due to the ZenBook duo not having an eternet port we need to establish a connection wirelessly.

Run `ip addr show` to show existing network adapters. There will a **_wlan0_** which we are going to use to connect via wifi.

To show available networks run `iwctl` which will open up a seperate console. And the type in `station wlan0 get-networks`

![arch start](assets/arch_installation/ip_addr_show_iwctl.png)

Connect to your network with:

``` shell
iwctl --passphrase "{{password}}" station wlan0 connect {{SSID}}
```

> [!NOTE]
> Replace {{password}} and {{SSID}} with your networks password and name.

<br>

> [!NOTE]
> You can run `ip addr show` to check weather there was a IP address assigned. Your IP will show up in the wlan0 section.

> [!TIP]
> Since a internet connection is now established you can also continue via another machine over ssh. <br>
> See [ssh_install.md](ssh_install.md) for further information an instructions.

### Installing Arch

Run `archinstall` to start the installation of arch linux


[^1]: https://www.asus.com/laptops/for-home/zenbook/zenbook-duo-ux481/helpdesk_bios/?model2Name=Zenbook-Duo-UX481
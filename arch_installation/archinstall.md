# Archinstall

Run `archinstall` to start a "guided" installation of Arch Linux.

``` shell
archinstall
```

![arch install](assets/archinstall/install.png)

## Archinstall language

- `Archinstall language` set to your needs

![install language](assets/archinstall/language/language.png)

## Locales

- `Locales` set to your keyboard layout and country specific settings

![locales](assets/archinstall/locales/locales.png)

## Mirrors and repositories

- `Mirrors and repositories` set `Select region` to your country

![mirrors and repositories](assets/archinstall/mirrors_regions/regions.png)
![region select](assets/archinstall/mirrors_regions/regions_select.png)

## Disk configuration

- `Disk configuration` best-effort default partition layout works. If you want to make incremental snapshots of your system. I recommend `btrfs` for the filesystem type. If choosen select `yes (default)` for the default structure and `Use compression` to enable CoW(Copy on Write)

> [!NOTE]
> Using `btrfs` allows you to make incremental snapshots of your system if setup corretly. This is something that can come in handy because of Arches rowling releases. <br>
> You can also choose the normal `ext4` filesystem.

![arch install](assets/archinstall/disk_configuration/disk_config_type.png)

![disk partitioning](assets/archinstall/disk_configuration/partitioning.png)

## Bootloader

- `Bootloader` set to `GRUB`

![select bootloader](assets/archinstall/bootloader/bootloader.png)

## Hostname

- `Hostname` set to your liking

## Authentication

- `Authentication` set up a password for root and create a new user that is a superuser

### Root

![authentication tab](assets/archinstall/authentication/root_account/rootpasswd.png)
![set root passwd](assets/archinstall/authentication/root_account/rootpassw_input.png)
![confirm passwd](assets/archinstall/authentication/root_account/rootpasswd_confirm.png)
![overview](assets/archinstall/authentication/root_account/rootpasswd_overview.png)

<br>

### User

![add user](assets/archinstall/authentication/user/useraccount_adduser.png)
![username](assets/archinstall/authentication/user/useraccount_username.png)
![passwd](assets/archinstall/authentication/user/useraccount_passwd.png)
![confirm passwd](assets/archinstall/authentication/user/useraccount_passwd_confirm.png)
![superuser selection](assets/archinstall/authentication/user/useraccount_superuser.png)
![superuser overview](assets/archinstall/authentication/user/useraccount_superuser_overview.png)

## Application

- `Applications` leave `Bluetooth` as is and inside `Audio` change to pipewire

![application selection](assets/archinstall/applications/applications_selection.png)

![select pipewire](assets/archinstall/applications/audio_pipewire.png)

## Kernels

- `Kernels` linux (default)

![kernel selection](assets/archinstall/kernels/kernels_selection.png)

## Network configuration

- `Network configuration` select `Use NetworkManager`

> [!NOTE]
> By choosing NetworkManager you can later configure network settings with a GUI inside your desktop environment.

## Timezone

- `Timezone` set to your timezone

You can now go back to the [main guide for installing Arch](./README.md#installing-arch).
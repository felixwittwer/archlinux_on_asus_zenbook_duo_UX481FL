# SSH install

## Check SSH status

Run: `systemctl status sshd` to check if the ssh service is running.

![ssh active](assets/ssh_install/ssh_active.png)

If for whatever reason ssh is not running start it with `systemctl start sshd`.

## Set temporary root password for SSH

Type:

```shell
passwd
```

and set your desired password.

> [!NOTE]
> The password set here will not be the root password that you will later use for your root user. This one here is only temporary.

## Connect to your machine

On a different machine open a comand prompt and type `ssh root@{{your ip}}`

> [!NOTE]
> Make sure to replace {{your ip}} with the one of your ZenBook Duo on which you want to install Arch. <br>
> You can see the IP address by typing `ip addr show`.

<br>

You can now go back to the [main guide for installing Arch](./README.md#installing-arch).
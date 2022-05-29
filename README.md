# Configure ParrotOS

## fastboot with autologin

In /etc/lightdm/lightdm.conf (under label: `[Seat:*]`)
```
autologin-user=my_username                                                   
autologin-user-timeout=2                                                 
autologin-in-background=true
```

## fastboot without grub timeout

In /etc/default/grub
```
GRUB_TIMEOUT=0
```
And run: `update-grub`

## sudo without type password

With `visudo` (at the end of file)
```
my_username ALL=(ALL:ALL) NOPASSWD: ALL
```

## access shared directory with normal user

`sudo usermod -a -G vboxsf my_username`

`reboot`

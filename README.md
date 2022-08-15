Dell IPMI Fan Control (R210II Branch)
====
This is a fork of [https://github.com/VV0JC13CH/DellIPMIFanCtrl](DellIPMIFanCtrl) dedicated to the specific Dell R210II unit.
Please read ### comments in fanctrl.rb in order to know differences between this and main branch.

Simple ruby script / systemd service for controlling fans with a fan profile on Dell servers.

Requires a linux host OS / hypervisor (such as proxmox or debian) with IPMI / iDRAC6 enabled.
Tested on a Dell R710, but should work with most 11-13th generation Poweredge machines.

## Install (with systemd)
Install the required packages:
```
apt install lm-sensors ipmitool ruby
```

Clone the repository, and run `ruby install.rb`

The service name is `fanctrl`, and can be managed through the usual suspects of systemctl, journalctl and the like.

You can change the fan profile by editing `fanctrl.rb`

## Run (without systemd)
You will have to run the script manually. You can run `ruby fanctrl.rb` in a cron-job or something similar.

## Credits
`u/tatmde` for the necessary IPMI commands https://www.reddit.com/r/homelab/comments/7xqb11/dell_fan_noise_control_silence_your_poweredge/

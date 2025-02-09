# cfg_debian
set Debian APT and Update config, no reboot. 

### run 
ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main cfg_debian.yml

Sets Debian default apt sources.list 
Set up Dayly updates without reboots. 
Set up this configuration every Day
Run @16 PM sets up this config, send mail if error 

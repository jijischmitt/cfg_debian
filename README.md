## Dep
apt install ansible

### cfg_debian.yml
set Debian APT and Update config, no reboot. 

#### run 
ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main set_apt_cfg.yml

- Sets Debian default apt sources.list 
- Set up Dayly updates without reboots. 
- Run @16 PM sets up this config, send mail if error 

### do_reboot.yml 
send reboot command 
ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main do_reboot.yml 

### do_dist_upgrade.yml
send dist upgrade command 
ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main do_dist_upgrade.yml

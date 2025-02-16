
## Dependencies

> apt install ansible

### Config Auto Update

 - Set up Debian/Ubuntu default apt sources.list
 - Update apt cache
 - Install unattended-upgrades package
 - Configure unattended-upgrades --> 50unattended-upgrades.j2
 - Enable unattended-upgrades
 - Sets up Cronjob 

> redo config every day @5 AM and send mail on error to root

 
  #### run

    ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main setup.yml

- Sets Debian default apt sources.list 
- Set up Daily updates without reboots. 
- Run @5 AM sets up this config, send mail if error 
- Check if reboot is requied, if so reboot.

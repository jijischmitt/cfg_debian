
## Dependencies

> apt install ansible

### Config Auto Update

 - Set up Debian/Ubuntu default apt sources.list
 - Update apt cache
 - Install unattended-upgrades package
 - Configure unattended-upgrades --> 50unattended-upgrades.j2
 - Enable unattended-upgrades
 - Sets up Cronjob 

> redo config every day @16H and send mail on error to root

 
  #### run

    ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main setup.yml

- Sets Debian default apt sources.list 
- Set up Dayly updates without reboots. 
- Run @16 PM sets up this config, send mail if error 

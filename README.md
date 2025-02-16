
## Dependencies

> apt install ansible

### Config Auto Update

 - Set up Debian/Ubuntu default apt sources.list
 - Update apt cache
 - Install unattended-upgrades package
 - Configure unattended-upgrades --> 50unattended-upgrades.j2
 - Enable unattended-upgrades
 - Sets up Cronjob 

> redo config every day @4 AM and send mail on error to root
 
  #### run

    ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main setup.yml

graph TD
    A[/"`ansible-pull -U https://github.com/jijischmitt/cfg_debian.git -C main setup.yml`"\]
    R1(("`Role apt_cfg`")) 
    R1Ta1[Set up Debian/Ubuntu default apt sources.list]
    R1Ta2[Update apt cache]
    R1Ta3[apt install unattended-upgrades needrestart]
    R1Ta4[Configure unattended-upgrades]
    R1Ta5[Enable unattended-upgrades]
    R1Ta6[Set up Cron, send mail on error ]
    R2(("`Role reboot_if_required`")) 
    R2ta1[Check if reboot file exists]
    R2ta2[Check if needrestart file exists]
    R2ta3[Reboot if required]
    
A --> R1
R1 --> R1Ta1 --> R1Ta2 --> R1Ta3 --> R1Ta4 --> R1Ta5 --> R1Ta6 
R1Ta6 --> R2
R2 --> R2ta1 --> R2ta2 --> R2ta3
R2ta3 -->|cron execution @4 AM | A




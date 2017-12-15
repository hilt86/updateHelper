### Playbooks to make your life easier

There are three playbooks that will make your life easier if you run Ubuntu:

1. checkForUpdates - logs a message if a server needs an update
2. checkForReboot - same as above but tell you if the server needs a reboot
3. updateUpgrade - will update packages but won't reboot the system
4. updateUpgradeReboot - will update packages and then reboot servers one by one 

The last script is probably the most helpful as it will wait for the server to come back up before proceeding to install updates to the next one - it does this using the "serial: 1" at the top of the playbook. It will also check that the host is up by using "wait\_for" at the end of the playbook. Some of my servers come up a little slower than others so you may have to play with the "delay" option here as if the host hasn't rebooted in time then you will have to re-run the playbook.


Disclaimer : the original idea for this came from [Chao Huang](https://realguess.net/2014/12/21/ansible-update-servers-to-the-latest-and-reboot/)

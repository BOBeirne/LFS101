- Much faster than [[init]] ,  `/sbin/init` now just points to `/lib/systemd/systemd` (systemd takes over)
- Takes advantage of aggressive parallelization techniques, which allows multiple services to be initiated at the same time 
- Replaced complicates shell scripts with config files
	- enumerate what needs to be done before service starts
	- how to set it up
	- what conditions service should indicate have been completed when start-up finishes.

### CLI

- `systemctl` command is used for most of the basic tasks
- using Apache `httpd` as an **example**
- in most cases `.service` can be omitted
- Ubuntu / SUSE : `apache2`
- Red Hat / CentOS : `httpd`

```bash
# starting, stopping and restarting the service
$ sudo systemctl start|stop|restart httpd.service # 

# emable/disale system service from starting up at the system boot
$ sudo systemctl enable|disable httpd.service

# Checking te service status
$ sudo systemcl status httpd.service 

```
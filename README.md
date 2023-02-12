# Chrony

Chrony is a Network Time Protocol (NTP) client. An NTP server allows all devices on a network to synchronize their time. This article explains how to install and configure Chrony on RHEL or Ubuntu.

## Install and Configure on Ubuntu

1. List the available time zones and choose your preference.

```
$ sudo timedatectl list-timezones
```

2. Set the server time zone. For example, change Asia/Kuala_Lumpur to your time zone

```
$ sudo timedatectl set-timezone Asia/Kuala_Lumpur
```

3. Update the system packages in the Ubuntu server.

```
$ sudo apt update
```

4. Install Chrony.

```
$ sudo apt install chrony -y
```

5. Start the Chrony service.

```
$ sudo systemctl start chronyd
```

6. Check the status of the service.

```
$ sudo systemctl status chronyd
```

7. Check the number of connected servers and peers.

```
$ chronyc activity
```

8. Show the statistics for each server.

```
$ chronyc sourcestats -v
```

9. Edit the Chrony configuration file.

```
$ sudo nano /etc/chrony/chrony.conf
```

10. Add the following code to the end of the file. Change 192.168.2.12 to your preferable NTP server's IP address. You can add other NTP servers by specifying their IP addresses.

```
server 192.168.2.12
```

11. Save and exit the file. Synchronize the servers.

```
$ sudo timedatectl set-ntp true
```

12. Restart the Chrony service.

```
$ sudo systemctl restart chronyd
```

13. Check the list of clients added.

```
$ sudo chronyc clients
```

14. Check the Chrony sources.

```
$ chronyc sources
```

15. Check the server chrony is tracking with its performance metrics.

```
$ chronyc tracking
```


## Install and Configure on RHEL





















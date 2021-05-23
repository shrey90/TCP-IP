# TCP-IP

Most of the Unix servers have no TCP IO 
buffer tuning and most of the unix server has default TCP IO receive and send buffers that are too small for the amount of data moved on database server, web server or WAS server or MQ server and SAP or SAS or Data Warehouse servers.

TCP IO Buffer setting that will 
improve and reduce p1, p2, p3 tickets – 
Server slow response times, or intermittent problem on server response, by 80%. Ability to move back up data in less time to backup device. Oracle, Sybase, Db2, Websphere, appache server and any in house application will see the benefit of TCP IO buffer setting increase from default settings.


For Red Hat Linux:

131071 is default value.

Double the value from 131071 to 262144

cat /proc/sys/net/core/rmem_max

131071 → 262144

cat /proc/sys/net/core/rmem_default

129024 → 262144

 cat /proc/sys/net/core/wmem_default

129024 → 262144

 cat /proc/sys/net/core/wmem_max

131071 → 262144



The default and maximum window size can be changed in the proc file system without reboot:

The default setting in bytes of the socket receive buffer:

# sysctl -w net.core.rmem_default=262144

The default setting in bytes of the socket send buffer:

# sysctl -w net.core.wmem_default=262144

The maximum socket receive buffer size which may be set by using the SO_RCVBUF socket option:

# sysctl -w net.core.rmem_max=262144

The maximum socket send buffer size which may be set by using the SO_SNDBUF socket option:

# sysctl -w net.core.wmem_max=262144

To make the change permanent, add the following lines to the /etc/sysctl.conf file, which is used during the boot process:

net.core.rmem_default=262144

net.core.wmem_default=262144

net.core.rmem_max=262144

net.core.wmem_max=262144



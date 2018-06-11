
# MySQL Server Opspack

MySQL is one of the most popular open-source relational database management systems (RDBMS) and is currently used by Facebook, Twitter, Flickr and Google to name but a few.  As of July 2013, it was officially the world’s second most widely used RDBMS.

It remains an extremely popular choice for web-based software applications and is a central component of LAMP. Fast, powerful, customizable and easy-to-use, MySQL should only become more utilized as a versatile tool with its future releases.

## What You Can Monitor

Opsview Monitor’s MySQL Opspack includes 39 performance metrics including connects, sessions, hits and free blocks. This allows you to make sure your database is running at full speed, enabling you to monitor any and every change over time with our Opsview Monitor Reporting Module.

## Service Checks

| Service Check | Description |
|:------------- |:----------- |
| Aborted connects|Number of aborted connects|
| Bytes received|Number of bytes received (total)    |
| Bytes sent|Number of bytes sent (total)    |
| Connections|Number of Connections    |
| DB Listener|Checks MySQL on TCP port 3306    |
| DB Processes|Checks MySQL processes    |
| Delayed errors|Delayed errors    |
| InnoDB Log Pending FSyncs|InnoDB Log pending fsyncs    |
| InnoDB Log Pending Writes|InnoDB Log pending writes  |
| InnoDB Pending Writes|InnoDB Log waits    |
| InnoDB Waits|InnoDB Log waits    |
| Key blocks not flushed|Key blocks not flushed  |  
| Key blocks unused|Key blocks unused    |
| Key blocks used|Key blocks used    |
| Key read requests|Key read requests    |
| Key reads|Key blocks unused    |
| Key write requests|Key write requests    |
| Key writes|Key writes    |
| Low memory prunes|Low memory prunes    |
| Max used connections|Maximum used connections |   
| Open Files|Open files on MySQL Server    |
| Open streams|Open streams MySQL Server  |  
| Open tables|MySQL open tables    |
| Qcache free blocks|Qcache free blocks |   
| Qcache free memory|Qcache free memory |   
| Qcache hits|Qcache hits    |
| Qcache inserts|Qcache inserts    |
| Qcache not cached|Qcache not cached    |
| Qcache queries incache|Qcache queries in cache    |
| Qcache total blocks|Qcache total blocks    |
| Slave open temp tables|Number of open temp tables on slaves    |
| Slave retried transactions|Number of retried transactions on slaves |   
| SSL Renegotiates|SSL connect renegotiates    |
| SSL Session cache hits|SSL sessions cache misses    |
| SSL Session cache misses|SSL sessions cache misses    |
| SSL Session cache overflows|SSL sessions cache overflows |
| SSL Session cache timeouts|SSL sessions cache timeouts  |  
| Threads connected|Number of threads connected   |
| Threads running|Threads running|

## Setup and Configuration

### Prerequisites

#### Network Dependencies

You will need to open port tcp/3306 from the Opsview Monitor server to the MySQL server host. See your operating system/firewall documentation for information on how to do this if your host is running a local firewall.

#### Installation

On the MySQL server to be monitored:

- Install the Opsview Agent

- Enable remote connections in MySQL, but ensure you have set a MySQL root password for security reasons ('mysql_secure_installation' may be available on your system to secure MySQL)

- Create a dedicated user within MySQL for use by monitoring (see here for more information). Suitable SQL to create an 'opsview' user might be (NOTE: set the <opsview server IP address> and <password> accordingly):
mysql> CREATE USER 'opsview'@'<opsview server IP address>' IDENTIFIED BY '<password>';
mysql> FLUSH PRIVILEGES;

To configure and utilize this Opspack, you simply need to add the 'Database - MySQL' Opspack to your Opsview Monitor system.

Step 1: Add the host template

![Add host template](/docs/img/add_mysql_host.png?raw=true)

Step 2: Add and configure variables required for this host

![Add variables](/docs/img/add_mysql_variables.png?raw=true)

Step 3: Reload and the system will now be monitored

![View Service Checks](/docs/img/view_mysql_service_checks.png?raw=true)

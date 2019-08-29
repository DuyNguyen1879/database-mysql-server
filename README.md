
# Database - MySQL Server Opspack

MySQL is one of the most popular open-source relational database management systems (RDBMS) and is currently used by Facebook, Twitter, Flickr and Google to name but a few.  As of July 2013, it was officially the world’s second most widely used RDBMS.

It remains an extremely popular choice for web-based software applications and is a central component of LAMP. Fast, powerful, customizable and easy-to-use, MySQL should only become more utilized as a versatile tool with its future releases.

## What You Can Monitor

Opsview Monitor’s MySQL Opspack includes 39 performance metrics including connects, sessions, hits and free blocks. This allows you to make sure your database is running at full speed, enabling you to monitor any and every change over time with our Opsview Monitor Reporting Module.

## Service Checks

| Service Check | Description |
|:------------- |:----------- |
| MYSQL Aborted connects | Number of aborted connects |
| MYSQL Bytes received | Number of bytes received (total) |
| MYSQL Bytes sent | Number of bytes sent (total) |
| MYSQL Connections | Number of Connections |
| MYSQL DB Listener | Checks MySQL on TCP port 3306 |
| MYSQL DB Processes | Checks MySQL processes    |
| MYSQL Delayed errors | Delayed errors |
| MYSQL InnoDB Log Pending FSyncs | InnoDB Log pending fsyncs |
| MYSQL InnoDB Log Pending Writes | InnoDB Log pending writes |
| MYSQL InnoDB Pending Writes | InnoDB Log waits |
| MYSQL InnoDB Waits | InnoDB Log waits |
| MYSQL Key blocks not flushed | Key blocks not flushed |
| MYSQL Key blocks unused | Key blocks unused |
| MYSQL Key blocks used | Key blocks used |
| MYSQL Key read requests | Key read requests |
| MYSQL Key reads | Key blocks unused |
| MYSQL Key write requests | Key write requests |
| MYSQL Key writes | Key writes |
| MYSQL Low memory prunes | Low memory prunes |
| MYSQL Max used connections | Maximum used connections |
| MYSQL Open Files | Open files on MySQL Server |
| MYSQL Open streams | Open streams MySQL Server |
| MYSQL Open tables | MySQL open tables    |
| MYSQL Qcache free blocks | Qcache free blocks |
| MYSQL Qcache free memory | Qcache free memory |
| MYSQL Qcache hits | Qcache hits |
| MYSQL Qcache inserts | Qcache inserts |
| MYSQL Qcache not cached | Qcache not cached |
| MYSQL Qcache queries incache | Qcache queries in cache |
| MYSQL Qcache total blocks | Qcache total blocks |
| MYSQL Slave open temp tables | Number of open temp tables on slaves |
| MYSQL Slave retried transactions | Number of retried transactions on slaves |
| MYSQL SSL Renegotiates | SSL connect renegotiates |
| MYSQL SSL Session cache hits | SSL sessions cache misses |
| MYSQL SSL Session cache misses | SSL sessions cache misses |
| MYSQL SSL Session cache overflows | SSL sessions cache overflows |
| MYSQL SSL Session cache timeouts | SSL sessions cache timeouts |
| MYSQL Threads connected | Number of threads connected |
| MYSQL Threads running | Threads running |

## Setup and Configuration

### Prerequisites

#### Network Dependencies

You will need to open port tcp/3306 from the Opsview Monitor server to the MySQL server host. See your operating system/firewall documentation for information on how to do this if your host is running a local firewall.

### Installation

#### On the MySQL server to be monitored:

Install the Opsview Agent

> For more information, refer to [Opsview Knowledge Center - Opsview Agents Installation](https://knowledge.opsview.com/docs/installing-opsview-agents).

Enable remote connections in MySQL, but ensure you have set a MySQL root password for security reasons ('mysql_secure_installation' may be available on your system to secure MySQL)

Create a dedicated user within MySQL for use by monitoring.
Suitable SQL to create an 'opsview' user might be:
```
mysql> CREATE USER 'opsview'@'<opsview server IP address>' IDENTIFIED BY '<password>';
mysql> FLUSH PRIVILEGES;
```

### Configuration

#### Step 1: Add the host template

Add the **Database - MySQL Server** Host Template to your Opsview Monitor host.

![Add host template](/docs/img/add_mysql_host.png?raw=true)

> For more information, refer to [Opsview Knowledge Center - Adding Host Templates to Hosts](https://knowledge.opsview.com/docs/host#section-host-templates)

#### Step 2: Add and configure variables required for this host

| Variable | Description |
|:------------- |:------------------ |
| MYSQLCREDENTIALS | Used in authenticating services with MySQL. Override the Username and Password with your credentials. |

![Add variables](/docs/img/add_mysql_variables.png?raw=true)

> For more information, refer to [Opsview Knowledge Center - Adding Variables to Hosts](https://knowledge.opsview.com/docs/adding-a-new-variable#section-adding-a-variable-to-a-host).

#### Step 3: Apply changes and the system will now be monitored

![View Service Checks](/docs/img/view_mysql_service_checks.png?raw=true)

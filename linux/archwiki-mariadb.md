# MariaDB

**MariaDB** is a reliable, high performance and full-featured database server which aims to be an 'always Free, backward compatible, drop-in' replacement to **MySQL**. Since 2013 MariaDB is Arch Linux's default implementation of MySQL.

<https://wiki.archlinux.org/title/MariaDB>

## Installation

**MariaDB** is the default implementation of MySQL in Arch Linux, provided with the **mariadb** package.

Install **mariadb**, and run the following command *before starting* the `mariadb.service`

``` sh
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
mariadb-secure-installation
```

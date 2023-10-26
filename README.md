# MD_MariaDB
https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-22-04
https://webdock.io/en/docs/how-guides/database-guides/how-enable-remote-access-your-mariadbmysql-database

Step 1 — Installing MariaDB
```bash
sudo apt update
sudo apt install mariadb-server
sudo mysql_secure_installation
```

```sudo mysql_secure_installation
Output
NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, you'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none):
```

```sudo mysql_secure_installation
Output
. . .
Setting the root password or using the unix_socket ensures that nobody
can log into the MariaDB root user without the proper authorisation.

You already have your root account protected, so you can safely answer 'n'.

Switch to unix_socket authentication [Y/n] n
```

```sudo mysql_secure_installation
Output
. . .
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] n
```

Step 2 — (Optional) Creating an Administrative User that Employs Password Authentication
```bash
sudo mariadb
```

````sudo mariadb
MariaDB [(none)]> GRANT ALL PRIVILEGES ON *.* TO 'admin'@'localhost' IDENTIFIED BY 'password' WITH GRANT OPTION;
````

```bash
MariaDB [(none)]> FLUSH PRIVILEGES;
```

```bash
sudo systemctl status mariadb
```

```vi
vi /etc/mysql/my.cnf
```

```"/etc/mysql/my.cnf" (new line)
bind-address = 0.0.0.0
```
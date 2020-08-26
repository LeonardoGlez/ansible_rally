# Installing MariaDB Server 10.5
To deploy MariaDB Community Server 10.5 on RHEL 8, first download and use the ```mariadb_repo_setup script``` to configure the MariaDB repositories for YUM:

```bash
$ wget https://downloads.mariadb.com/MariaDB/mariadb_repo_setup
$ chmod +x mariadb_repo_setup
$ sudo ./mariadb_repo_setup
```

To avoid conflict with the OS-vendor packages, install dependencies separately and use the --repo flag to specify the repository:

```bash
$ sudo yum install perl-DBI libaio libsepol lsof boost-program-options
$ sudo yum install --repo="mariadb-main" MariaDB-server
```

Start the systemd service for MariaDB Server using systemctl:

```bash
$ sudo systemctl start mariadb.service
```

To probe de installation:

```bash
$ sudo mysql
```

To quit:
```bash
MariaDB [(none)]> quit
```

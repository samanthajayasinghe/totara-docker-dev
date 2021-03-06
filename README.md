### Container versions and build status:
Name | Version | Dockerfile | Build
--- | --- | --- | ---
nginx | 1.13.x | [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/nginx/Dockerfile) | [![Build status Nginx](https://img.shields.io/docker/build/derschatta/totara-dev-nginx.svg)](https://hub.docker.com/r/derschatta/totara-dev-nginx/)
php54 | 5.4 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php54/Dockerfile) | [![Build status PHP 5.4](https://img.shields.io/docker/build/derschatta/totara-dev-php54.svg)](https://hub.docker.com/r/derschatta/totara-dev-php54/)
php54-debug | 5.4 + xdebug 2.4.1 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php54-debug/Dockerfile) | [![Build status PHP 5.4 Debug](https://img.shields.io/docker/build/derschatta/totara-dev-php54-debug.svg)](https://hub.docker.com/r/derschatta/totara-dev-php54-debug/)
php55 | 5.5 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php55/Dockerfile) | [![Build status PHP 5.5](https://img.shields.io/docker/build/derschatta/totara-dev-php55.svg)](https://hub.docker.com/r/derschatta/totara-dev-php55/)
php55-debug | 5.5 + xdebug 2.5.5 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php55-debug/Dockerfile) | [![Build status PHP 5.5 Debug](https://img.shields.io/docker/build/derschatta/totara-dev-php55-debug.svg)](https://hub.docker.com/r/derschatta/totara-dev-php55-debug/)
php56 | 5.6 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php56/Dockerfile) | [![Build status PHP 5.6](https://img.shields.io/docker/build/derschatta/totara-dev-php56.svg)](https://hub.docker.com/r/derschatta/totara-dev-php56/)
php56-debug | 5.6 + xdebug 2.5.5 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php56-debug/Dockerfile) | [![Build status PHP 5.6 Debug](https://img.shields.io/docker/build/derschatta/totara-dev-php56-debug.svg)](https://hub.docker.com/r/derschatta/totara-dev-php56-debug/)
php70 | 7.0 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php70/Dockerfile) | [![Build status PHP 7.0](https://img.shields.io/docker/build/derschatta/totara-dev-php70.svg)](https://hub.docker.com/r/derschatta/totara-dev-php70/)
php70-debug | 7.0 + xdebug 2.6.0 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php70-debug/Dockerfile) | [![Build status PHP 7.0 Debug](https://img.shields.io/docker/build/derschatta/totara-dev-php70-debug.svg)](https://hub.docker.com/r/derschatta/totara-dev-php70-debug/)
php71 | 7.1 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php71/Dockerfile) | [![Build status PHP 7.1](https://img.shields.io/docker/build/derschatta/totara-dev-php71.svg)](https://hub.docker.com/r/derschatta/totara-dev-php71/)
php71-debug | 7.1 + xdebug 2.6.0 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php71-debug/Dockerfile) | [![Build status PHP 7.1 Debug](https://img.shields.io/docker/build/derschatta/totara-dev-php71-debug.svg)](https://hub.docker.com/r/derschatta/totara-dev-php71-debug/)
php72 | 7.2 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php72/Dockerfile) | [![Build status PHP 7.2](https://img.shields.io/docker/build/derschatta/totara-dev-php72.svg)](https://hub.docker.com/r/derschatta/totara-dev-php72/)
php72-debug | 7.2 + xdebug 2.6.0 |  [Dockerfile](https://github.com/derschatta/totara-docker-dev/blob/master/php/php72-debug/Dockerfile) | [![Build status PHP 7.2 Debug](https://img.shields.io/docker/build/derschatta/totara-dev-php72-debug.svg)](https://hub.docker.com/r/derschatta/totara-dev-php72-debug/)

## A Docker setup for local Totara Learn development

This project aims to provide an easy way to start developing for Totara by providing a Docker setup.

This setup was created and tested intensively on a MAC and Linux. It works on Windows as well but wasn't tested that much yet.

Although this project started as a development environment for Totara Learn it can be used for any other PHP project.

### What you get:
 * [NGINX](https://nginx.org/) as a webserver
 * [PHP](http://php.net/) 5.4, 5.5, 5.6, 7.0, 7.1, 7.2 to test for different versions
 * [PostgreSQL](https://www.postgresql.org/) (9.3.x and 10.x), [MariaDB](https://mariadb.org/) (10.2.x) and [MySQL](https://www.mysql.com/) (5.7.x), and [Microsoft SQL Server 2017](https://www.microsoft.com/en-us/sql-server/sql-server-2017) support
 * A [PHPUnit](https://phpunit.de/) and [Behat](http://behat.org/en/latest/) setup to run tests (including [Selenium](https://www.seleniumhq.org/))
 * A [mailcatcher](https://mailcatcher.me/) instance to inspect mails
 * [Redis](https://redis.io/) for caching and/or session handling
 * [XHProf](https://github.com/tideways/php-xhprof-extension) for profiling
 * [XDebug](https://xdebug.org/) installed, ready for debugging with your favorite IDE

### Requirements:
 * Totara source code: https://help.totaralearning.com/display/DEV/Getting+the+code
 * Docker: https://www.docker.com (for Docker on Mac please read warning below)
 * Docker-compose: https://docs.docker.com/compose/install (included in Docker for Mac/Windows)
 * Docker-sync: http://docker-sync.io/ (optional, for more speed on Mac)
 * At least 3.25GB of RAM for MSSQL

> ##### Warning Docker for Mac
> Please note that there's a current [issue with docker-sync](https://github.com/EugenMayer/docker-sync/issues/517) on Mac and Docker stable versions newer than [17.09.1-ce-mac42](https://docs.docker.com/docker-for-mac/release-notes/#docker-community-edition-17091-ce-mac42-2017-12-11-stable). To be on the safe side I recommend to download and installing this version. In the edge version [18.05.0-ce-mac67 and newer](https://docs.docker.com/docker-for-mac/edge-release-notes/#docker-community-edition-18050-ce-mac67-2018-06-07) the issue seem to be fixed as well.

### Installation:
 1. Clone the Totara source code (see requirements) 
 1. Clone this project
 1. Install docker-sync (optionally, recommended for MAC)
 1. Copy the file __.env.dist__ to __.env__ and change at least the path to your local Totara source folder (LOCAL_SRC)

#### /etc/hosts
Make sure you have all the hosts in your /etc/hosts file to be able to access them via the browser.

__Example:__
```bash
127.0.0.1   localhost totara54 totara54.behat totara55 totara55.behat totara56 totara56.behat totara70 totara70.behat totara71 totara71.behat totara72 totara72.behat
```

### Shortcut commands

This project comes with a few bash scripts to simplify usage accross platforms. The scripts are located in the **bin/** folder. Ideally you add the bin folder to your PATH environment variable so you can run the commands from anywhere.

```bash
tdocker                           # shortcut to general docker-compose ... command
tup [containers]                  # start (all) container(s)            
tbash [container]                 # log into a container, i.e. php-7.2
tstop [container]                 # stop (all) container(s)
trestart [container]              # restart (all) container(s)
tdown                             # shutdown all containers
tstats                            # show docker stats including container names
tbuild [container]                # build (all) container(s)
tgrunt [subfolder]                # run grunt scripts in container, if you use subfolders for version pass it as 2nd argument
tscale [container]=6              # scale up the number of containers, i.e. selenium-chrome
tunit [container] [folder] [init] # run or init unit tests in given container for given version
```

### Run

```bash
# if you use docker-sync, fire up docker-sync as a daemon in the background
docker-sync start
```

```bash
# start all containers in background
tup
# to limit the amount of containers fired up
# you can just start the db and php container of your choice,
# it automatically starts nginx container as well
tup pgsql php-7.2
# if you later need to access any other php container 
# just start it with
tup php-5.6
```

### Build

By default prebuilt images from docker hub (https://hub.docker.com/u/derschatta/) will be used. If you want to modify any of the containers to your needs then you can rebuild them locally with the following command:

```bash
tbuild
# or for individual images
tbuild php-7.2
```

### Config & Database

Make sure you have configured Totara and created the databases you need. You can connect to the databases from your host using any tools you prefer (host = _localhost_, use defautls ports).

#### Credentials

DB | Host | User | Password
--- | --- | --- | ---
**PostresSQL 10.x** | pgsql | postresql | 
**PostresSQL 9.3.x** | pgsql93 | postresql | 
**Mysql** | mysql | root | root
**MariaDB** | mariadb | root | root
**Mssql** | mssql | SA | Totara.Mssql1

To use the command line clients provided by the containers you can use the following commands:

```bash
# PostgreSQL
tdocker exec pgsql psql -U postgres

# MySQL / MariaDB
tdocker exec mysql mysql -u root -p"root"
tdocker exec mariadb mysql -u root -p"root"

# Microsoft SQL Server
tdocker exec php-7.1 /opt/mssql-tools/bin/sqlcmd -S mssql -U SA -P "Totara.Mssql1"
```

Create a database schema for each Totara version you would like to develop on.

#### data directories

The nginx container automatically creates all required data folders.

```bash
/var/www/totara/data/ver[versionnumber].[database]
/var/www/totara/data/ver[versionnumber].[database].phpunit
/var/www/totara/data/ver[versionnumber].[database].behat
# example
/var/www/totara/data/ver11.pgsql
/var/www/totara/data/ver11.pgsql.phpunit
/var/www/totara/data/ver11.pgsql.behat
```

versionnumber = 22, 24, 25, 26, 27, 29, 9, 10, 11, 12
database = pgsql, mysql, mssql

#### Config example

This is an example for the t11 branch with the 3 different databases and the correct data directories. Please note: You will need additional configuration parameters for PHPUnit and Behat. Please refer to Totara docs and have a look at config-dist.php for examples.

```php
//=========================================================================
// 1. DATABASE SETUP
//=========================================================================
// First, you need to configure the database where all Moodle data       //
// will be stored.  This database must already have been created         //
// and a username/password created to access it.                         //


//$CFG->dbtype    = 'mysqli';
//$CFG->dbhost    = 'mysql';  // eg 'localhost' or 'db.isp.com' or IP
//$CFG->dbuser    = 'root';   // your database username
//$CFG->dbpass    = 'root';   // your database password
//$CFG->dataroot  = '/var/www/totara/data/ver11.mysql';
//$CFG->behat_dataroot = '/var/www/totara/data/ver11.mysql.behat';
//$CFG->phpunit_dataroot = '/var/www/totara/data/ver11.mysql.phpunit';

//$CFG->dbtype    = 'sqlsrv';
//$CFG->dbhost    = 'mssql';  // eg 'localhost' or 'db.isp.com' or IP
//$CFG->dbuser    = 'SA';   // your database username
//$CFG->dbpass    = 'Totara.Mssql1';   // your database password
//$CFG->dataroot  = '/var/www/totara/data/ver11.mssql';
//$CFG->behat_dataroot = '/var/www/totara/data/ver11.mssql.behat';
//$CFG->phpunit_dataroot = '/var/www/totara/data/ver11.mssql.phpunit';

$CFG->dbtype    = 'pgsql';      // 'pgsql', 'mariadb', 'mysqli', 'mssql', 'sqlsrv'
$CFG->dbhost    = 'pgsql';  // eg 'localhost' or 'db.isp.com' or IP
$CFG->dbuser    = 'postgres';   // your database username
$CFG->dbpass    = '';   // your database password
$CFG->dataroot  = '/var/www/totara/data/ver11.pgsql';
$CFG->behat_dataroot = '/var/www/totara/data/ver11.pgsql.behat';
$CFG->phpunit_dataroot = '/var/www/totara/data/ver11.pgsql.phpunit';


$CFG->dblibrary = 'native';     // 'native' only at the moment
$CFG->dbname    = 'totara_11';     // database name, eg moodle
$CFG->prefix    = 'mdl_';       // prefix to use for all table names
$CFG->dboptions = array(
    'dbpersist' => false,       // should persistent database connections be
                                //  used? set to 'false' for the most stable
                                //  setting, 'true' can improve performance
                                //  sometimes
    'dbsocket'  => false,       // should connection via UNIX socket be used?
                                //  if you set it to 'true' or custom path
                                //  here set dbhost to 'localhost',
                                //  (please note mysql is always using socket
                                //  if dbhost is 'localhost' - if you need
                                //  local port connection use '127.0.0.1')
    'dbport'    => '',          // the TCP port number to use when connecting
                                //  to the server. keep empty string for the
                                //  default port
);
```


### Run unit tests

Make sure your config file contains the PHPUnit configuration needed and the database is ready.

**Initiate:**
```bash
# assuming you have a subfolder called 11 then you can call
# to initiate the unit tests
tunit php-7.1 11 init
```
**Run:**
```bash
# run all unit tests in given container for version
tunit php-7.1 11
# or add more phpunit params
tunit php-7.1 11 --test-suffix=_test.php relative/path/to/tests/
```

### Run behat tests

Make sure your config file contains the Behat configuration needed and the database is ready.

Log into one of the test containers
```bash
tbash php-5.6
tbash php-7.1
# or if you need xdebug support
tbash php-5.6-debug
tbash php-7.1-debug
```

Go to the project folder
```bash
# replace version
cd /var/www/totara/src/[version]
```

If needed run the init script to initiate the behat tests
```bash
# in the project folder
php composer.phar install
# initiate the test environment (use --parallel=x if needed)
php admin/tool/behat/cli/init.php
```

To start running
```bash
# for t11
vendor/bin/behat
# for others use the command prompted after init, for example:
vendor/bin/behat --config /var/www/totara/data/ver9.pgsql.behat/behatrun/behat/behat.yml
```

### Switch between different versions

I recommend to check out each Totara Learn version in a different subfolder below the folder LOCAL_SRC defined in .env. This is just a suggestion which worked fine for me. There are different ways to handle this and at the end you need to decide yourself how to do it.

# Mailcatcher

The setup comes with mailcatcher support. Just add the following to your config and all mails will be sent to it:

```php
$CFG->smtphosts = 'mailcatcher:25';
```

Open __http://localhost:8080__ to open the mailcatcher GUI.

If needed, modify the local port in the docker-compose.yml file.

# NodeJS, NPM and grunt 

If you want to use grunt or npm you can log into the nodejs container and issue the commands there:

```bash
tdocker run nodejs bash
# go to your source directory and
npm install
npm install grunt-cli
./node_modules/.bin/grunt
```

Or you use the shortcut bash script:

```bash
tgrunt
tgrunt 12
``` 

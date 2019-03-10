---
title: "Mycli - productive mysql command line client"
date: 2019-03-10T16:59:28+08:00
draft: false
categories: [database]
tags: [mysql,sql]
---

As I know there are two MySQL client:

* [MySQL workbench](https://www.mysql.com/products/workbench/) is a GUI client which is developed by official.
* [mycli](https://github.com/dbcli/mycli) is a terminal client which is an open source & developed by python. 

There are two reasons why I choose `mycli` as my primary MySQL client:

1. I prefer to use command line interface
2. mycli supports `auto-completion` and `syntax highlighting`

## Brief Usage 
```
$ mycli --help
Usage: mycli [OPTIONS] [DATABASE]

  A MySQL terminal client with auto-completion and syntax highlighting.

  Examples:
    - mycli my_database
    - mycli -u my_user -h my_host.com my_database
    - mycli mysql://my_user@my_host.com:3306/my_database

Options:
  -h, --host TEXT               Host address of the database.
  -P, --port INTEGER            Port number to use for connection. Honors
                                $MYSQL_TCP_PORT.
  -u, --user TEXT               User name to connect to the database.
  -p, --password TEXT           Password to connect to the database.
  -d, --dsn TEXT                Use DSN configured into the [alias_dsn]
                                section of myclirc file.
  --list-dsn                    list of DSN configured into the [alias_dsn]
                                section of myclirc file.
```

## Configuration
* the location of configuration file is at `~/.myclirc`

### Setup `DSN`

Development process may include different phase such as local, beta, production, it means there are lots of mysql server host need to remember.

It will be useful if setting up `alias_dsn` in the config. After that we can use `-d` option to connect to correspond server quickly.

for example:

```
[alias_dsn]
local = mysql://[user[:password]@][localhost][:port][/dbname]
beta = mysql://[user[:password]@][betahost][:port][/dbname]
production = mysql://[user[:password]@][productionhost][:port][/dbname]
```

The correspond usage of mycli will be:
```
mycli -d local
mycli -d beta
mycli -d production
```

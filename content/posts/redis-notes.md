---
title: "Redis Notes"
author: "hp.huang"
date: 2019-03-04T23:17:50+08:00
draft: false
categories: [database]
tags: [redis,nosql]
---

# Installation

```
brew install redis
```

# Redis-cli
redis-cli is the Redis command line interface which allow you interact with redis server see on [offcial site](https://redis.io/topics/rediscli)

## connect to server
```
redis-cli -h yourHost -p yourPort

# enable cluster mode
redis-cli -c -h yourHost -p yourPort
```

## all usage
```
Usage: redis-cli [OPTIONS] [cmd [arg [arg ...]]]
  -h <hostname>    Server hostname (default: 127.0.0.1)
  -p <port>        Server port (default: 6379)
  -s <socket>      Server socket (overrides hostname and port)
  -a <password>    Password to use when connecting to the server
  -r <repeat>      Execute specified command N times
  -i <interval>    When -r is used, waits <interval> seconds per command.
                   It is possible to specify sub-second times like -i 0.1
  -n <db>          Database number
  -x               Read last argument from STDIN
  -d <delimiter>   Multi-bulk delimiter in for raw formatting (default: \n)
  -c               Enable cluster mode (follow -ASK and -MOVED redirections)
  --raw            Use raw formatting for replies (default when STDOUT is not a tty)
  --latency        Enter a special mode continuously sampling latency
  --slave          Simulate a slave showing commands received from the master
  --rdb <filename> Transfer an RDB dump from remote server to local file.
  --pipe           Transfer raw Redis protocol from stdin to server
  --bigkeys        Sample Redis keys looking for big keys
  --eval <file>    Send an EVAL command using the Lua script at <file>
  --help           Output this help and exit
  --version        Output version and exit

Examples:
  cat /etc/passwd | redis-cli -x set mypasswd
  redis-cli get mypasswd
  redis-cli -r 100 lpush mylist x
  redis-cli -r 100 -i 1 info | grep used_memory_human:
  redis-cli --eval myscript.lua key1 key2 , arg1 arg2 arg3
  (Note: when using --eval the comma separates KEYS[] from ARGV[] items)

When no command is given, redis-cli starts in interactive mode.
Type "help" in interactive mode for information on available commands.
```

# Data Types
to be continued...

## Redis Persistence 
When using redis as `primary data store`, how to do the backup mechanism for data becomes very important. Redis prodvides two kind pesistence options: `RDB` and `AOF`. see more on [offical site](https://redis.io/topics/persistence)

# Redis Cluster
see [specification](https://redis.io/topics/cluster-spec)

# Other
- Redis Cheetsheet
   - https://www.cheatography.com/tasjaevan/cheat-sheets/redis/
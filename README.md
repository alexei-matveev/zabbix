#### Zabbix Module Quick Start

This file is not a part of the official Zabbix Sources.  See original
[README](./README) for licence and pointers.

Initial clone from GitHub for Speed, also it is a shallow one:

    git clone --depth 100 https://github.com/zabbix/zabbix.git
    git remote add github-mirror https://github.com/zabbix/zabbix.git
    git remote add zabbix-com https://git.zabbix.com/scm/zbx/zabbix.git
    git fetch --depth 100 github-mirror release/4.0
    git fetch --depth 100 zabbix-com release/4.0

Loadable Moudle see
[Docs](https://www.zabbix.com/documentation/4.0/manual/config/items/loadablemodules).

Start a local branch off 4.0 LTS:

    git checkout -b am/test-module github-mirror/release/4.0

And build the dummy module:

    aptitude install automake pkgconf make
    ./bootstrap.sh
    ./configure
    cd src/modules/dummy/
    make
    nm dummy.so

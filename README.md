## influxdb

[![Build Status](https://travis-ci.org/Oefenweb/ansible-influxdb.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-influxdb) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-influxdb-blue.svg)](https://galaxy.ansible.com/Oefenweb/influxdb)

Set up (the latest version of) [InfluxDB](https://www.influxdata.com/) in Debian-like systems.

#### Requirements

None

#### Variables

* `influxdb_install`: [default: `[]`]: Additional packages to install

* `influxdb_user`: [default: `influxdb`]: User to run daemon as
* `influxdb_group`: [default: `influxdb`]: Group to run daemon as

* `influxdb_meta_dir`: [default: `/var/lib/influxdb/meta`]: Meta directory
* `influxdb_data_dir`: [default: `/var/lib/influxdb/data`]: Data directory
* `influxdb_data_wall_dir`: [default: `/var/lib/influxdb/wal`]: Write-ahead logging (WAL) directory

* `influxdb_etc_default`: [`default: `[]`]: Content (lines) of `/etc/default/influxdb`

* `influxdb_etc_influxdb_influxdb_conf`: [see: `defaults/main.yml]: Content (lines) of `/etc/influxdb/influxdb.conf` ([see](https://docs.influxdata.com/influxdb/v1.4/administration/config/))

* `influxdb_databases_present`: [default: `[]`]: Databases to `CREATE`
* `influxdb_databases_present.{n}.name`: [required]: The name of the database
* `influxdb_databases_present.{n}.duration`: [optional]: Determines how long InfluxDB keeps the data (e.g. `1d`, `INF`)

* `influxdb_databases_absent`: [default: `[{name: test}]`]: Databases to `DROP`
* `influxdb_databases_absent.{n}.name`: [required]: The name of the database

## Dependencies

None

#### Example(s)

##### Simple

```yaml
---
- hosts: all
  roles:
    - influxdb
```

##### Custon configuration

```yaml
---
- hosts: all
  roles:
    - influxdb
  vars:
    influxdb_etc_influxdb_influxdb_conf:
      - |
        bind-address = "127.0.0.1:8088"
        [meta]
          dir = "{{ influxdb_meta_dir }}"
        [data]
          dir = "{{ influxdb_data_dir }}"
          wal-dir = "{{ influxdb_data_wal_dir }}"
```

#### License

MIT

#### Author Information

* Mark van Driel
* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-influxdb/issues)!

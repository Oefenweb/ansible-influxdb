## influxdb

[![Build Status](https://travis-ci.org/Oefenweb/ansible-influxdb.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-influxdb) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-influxdb-blue.svg)](https://galaxy.ansible.com/Oefenweb/influxdb)

Set up (the latest version of) [InfluxDB](https://www.influxdata.com/) in Debian-like systems.

#### Requirements

None

#### Variables

* `influxdb_install`: [default: `[]`]: Additional packages to install

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
  vars: {}
```

#### License

MIT

#### Author Information

* Mark van Driel
* Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-influxdb/issues)!

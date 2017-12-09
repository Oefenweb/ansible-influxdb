## ubuntu-1604-influxdb

Set up the latest stable version of InfluxDB on Ubuntu 16.04.

#### Requirements

* `python-httplib2` (will be installed)

#### Variables

* `ubuntu_1604_influxdb_databases_present`: [default: `[]`]: Names of the databases to `CREATE`
* `ubuntu_1604_influxdb_databases_absent`: [default: `[]`]: Names of the databases to `DROP`

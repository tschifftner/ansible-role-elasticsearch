# Ansible Role: Install ElasticSearch 6.x

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-elasticsearch.svg?branch=master)](https://travis-ci.org/tschifftner/ansible-role-elasticsearch)

Installs ElasticSearch 6.x from source on Debian/Ubuntu linux servers.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
elasticsearch_main_version: 6

```

Configuration:

```
elasticsearch_host: 'localhost'
elasticsearch_port: 9200

# settings for /etc/elasticsearch/elasticsearch.yml
elasticsearch_config:
#  - { regexp: '^script\.disable_dynamic', line: 'script.disable_dynamic: true' }
  - { regexp: 'network\.host', line: 'network.host: {{ elasticsearch_host }}' }
  - { regexp: 'http\.port', line: 'http.port: {{ elasticsearch_port }}' }

# settings for /etc/default/elasticsearch
elasticsearch_defaults:
  - { regexp: '^ES_HOME=', line: 'ES_HOME=/usr/share/elasticsearch' }
  - { regexp: '^CONF_DIR=', line: 'CONF_DIR=/etc/elasticsearch' }
  - { regexp: '^DATA_DIR=', line: 'DATA_DIR=/var/lib/elasticsearch' }
  - { regexp: '^LOG_DIR=', line: 'LOG_DIR=/var/log/elasticsearch' }
  - { regexp: '^PID_DIR=', line: 'PID_DIR=/var/run/elasticsearch' }
  - { regexp: '^ES_RESTART_ON_UPGRADE=', line: 'ES_RESTART_ON_UPGRADE=true' }
  - { regexp: '^ES_USER=', line: 'ES_USER=elasticsearch' }
  - { regexp: '^ES_GROUP=', line: 'ES_GROUP=elasticsearch' }
  - { regexp: '^ES_STARTUP_SLEEP_TIME=', line: 'ES_STARTUP_SLEEP_TIME=5' }
```

## Dependencies

- [tschifftner.java](https://github.com/tschifftner/ansible-role-java)

## Installation

```
$ ansible-galaxy install tschifftner.elasticsearch
```

## Example Playbook

    - hosts: server
      roles:
        - { role: tschifftner.elasticsearch }

## Supported OS

 - Debian 9 (Stretch)
 - Debian 8 (Jessie)
 - Ubuntu 18.04 (Bionic Beaver)
 - Ubuntu 16.04 (Xenial Xerus)
 
## Required ansible version

Ansible 2.5+

## License

[MIT License](http://choosealicense.com/licenses/mit/)

## Author Information

 - [Tobias Schifftner](https://twitter.com/tschifftner), [ambimax® GmbH](https://www.ambimax.de)
# Ansible Role: Install ElasticSearch 6.x

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-elasticsearch.svg?branch=master)](https://travis-ci.org/tschifftner/ansible-role-elasticsearch)

Installs ElasticSearch 6.x from source on Debian/Ubuntu linux servers.

## Requirements

None

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

```
elasticsearch_aptkey_url: "https://packages.elastic.co/GPG-KEY-elasticsearch"
elasticsearch_apt_repository: "deb http://packages.elastic.co/elasticsearch/2.x/debian stable main"
elasticsearch_config:
  - { regexp: '^script\.disable_dynamic', line: 'script.disable_dynamic: true' }
  - { regexp: 'network\.host', line: 'network.host: localhost' }
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
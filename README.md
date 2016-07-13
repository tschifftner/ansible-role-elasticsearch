# Ansible Role: Install ElasticSearch 2.x

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-elasticsearch.svg)](https://travis-ci.org/tschifftner/ansible-role-elasticsearch)

Installs ElasticSearch 2.x from source on Debian/Ubuntu linux servers.

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

None.

## Installation

```
$ ansible-galaxy install tschifftner.elasticsearch
```

## Example Playbook

    - hosts: server
      roles:
        - { role: tschifftner.elasticsearch }

## Supported OS

Ansible          | Debian Jessie    | Ubuntu 14.04    | Ubuntu 12.04
:--------------: | :--------------: | :-------------: | :-------------: 
2.1           | Yes              | Yes             | Yes

## License

MIT / BSD

## Author Information

 - [Tobias Schifftner](https://twitter.com/tschifftner), [ambimax® GmbH](https://www.ambimax.de)
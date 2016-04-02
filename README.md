# Ansible Role: Install ElasticSearch 2.x

[![Build Status](https://travis-ci.org/tschifftner/ansible-role-elasticsearch.svg)](https://travis-ci.org/tschifftner/ansible-role-elasticsearch)

Installs ElasticSearch 2.x from source on Debian/Ubuntu linux servers.

## Requirements

ansible 1.7+

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
$ ansible-galaxy install tschifftner.java
```

## Example Playbook

    - hosts: server
      roles:
        - { role: tschifftner.elasticsearch }

## Supported OS

Ansible          | Debian Jessie    | Ubuntu 14.04    | Ubuntu 12.04
:--------------: | :--------------: | :-------------: | :-------------: 
1.7              | Yes              | Yes             | Yes
1.8              | Yes              | Yes             | Yes
1.9              | Yes              | Yes             | Yes
2.0.1*           | Yes              | Yes             | Yes

*) 2.0.0.0, 2.0.0.1, 2.0.0.2 are not supported!

## License

MIT / BSD

## Author Information

 - Tobias Schifftner, @tschifftner
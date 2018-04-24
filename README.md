## php-cli-ondrej 

[![Build Status](https://travis-ci.org/Oefenweb/ansible-php-cli-ondrej.svg?branch=master)](https://travis-ci.org/Oefenweb/ansible-php-cli-ondrej) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-php--56--cli-blue.svg)](https://galaxy.ansible.com/tersmitten/php-cli-ondrej)

Set up PHP Cli in Ubuntu systems (using Ondřej Surý's ppa).

#### Requirements

None

#### Variables

* `php_cli_ondrej_version`: [default: `5.6`]: Version to install (e.g. `7.0`, `7.1`, `7.2`)

* `php_cli_ondrej_install`: [default: `[]`]: (Additional) Packages to install

* `php_cli_ondrej_update_alternatives`: [default: `true`]: Whether or not to run `update-alternatives`

* `php_cli_ondrej_precision`: [default: `14`]: The number of significant digits displayed in floating point numbers
* `php_cli_ondrej_serialize_precision`: [default: `17`, `-1` since `7.1`]: When floats & doubles are serialized store serialize_precision significant digits after the floating point
* `php_cli_ondrej_disable_functions`: [default: `[]`]: This directive allows you to disable certain functions for security reasons
* `php_cli_ondrej_max_execution_time`: [default: `0`]: Maximum execution time of each script, in seconds
* `php_cli_ondrej_memory_limit`: [default: `-1`]: Maximum amount of memory a script may consume
* `php_cli_ondrej_error_reporting`: [default: `E_ALL & ~E_DEPRECATED & ~E_STRICT`]: This directive informs PHP of which errors, warnings and notices you would like it to take action for
* `php_cli_ondrej_openssl_cafile`: [optional]: The location of a Certificate Authority (CA) file on the local filesystem (since `5.6`)
* `php_cli_ondrej_openssl_capath`: [optional]: The location of a Certificate Authority (CA) directory on the local filesystem (since `5.6`)

* `php_cli_ondrej_mods_present`: [default: `[{name: json}, {name: xml}, {name: readline}, {name: mysql}, {name: memcache}, {name: memcached}, {name: msgpack}, {name: mstring}, {name: mcrypt}, {name: gd}, {name: curl}]`]: Modules to install (and enable)
* `php_cli_ondrej_mods_present.{n}.name`: [required]: The identifier of the module (e.g. `curl`)
* `php_cli_ondrej_mods_present.{n}.dependencies`: [optional: default: `[]`]: Packages needed by the module (e.g. `php5.6-curl`)
* `php_cli_ondrej_mods_present.{n}.state`: [optional, default `enabled`]: Modules to disable (e.g. `{name: xdebug, state: disabled}`)

* `php_cli_ondrej_mods_absent`: [default: `[{name: opcache}]`]: Modules to disable
* `php_cli_ondrej_mods_absent.{n}.name`: [required]: The identifier of the module (e.g. `opcache`)

#### Dependencies

None

#### Example(s)

##### Simple

```yaml
---
- hosts: all
  roles:
    - php-cli-ondrej
```

##### Multiple versions

```yaml
---
- hosts: all
  roles:
    - role: php-cli-ondrej
      php_cli_ondrej_version: 7.0
      php_cli_ondrej_update_alternatives: false

    - role: php-cli-ondrej
      php_cli_ondrej_version: 5.6
```

#### License

MIT

#### Author Information

Mischa ter Smitten

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Oefenweb/ansible-php-cli-ondrej/issues)!

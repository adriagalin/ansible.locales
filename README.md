adriagalin.locales
=========

[![Build Status](https://travis-ci.org/adriagalin/ansible.locales.svg?branch=master)](https://travis-ci.org/adriagalin/ansible.locales) [![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-locales-blue.svg)](https://galaxy.ansible.com/list#/roles/4785)

An ansible role to install the locales package and set up your system's locale.

Requirements
------------

Tested on:

Ubuntu 14.04 LTS

Should work with:

All Ubuntu

Role Variables
--------------

```yaml
# the amount in seconds to cache apt-update.
ag_apt_cache_valid_time: 3600

# the locale file.
ag_locale_config_path: /var/lib/locales/supported.d/local

# the language packs that you want to install.
ag_locales_language_packs_present:
  - { language: language-pack-en, state: latest }
  - { language: language-pack-en-base, state: latest }

# the language packs that you want to remove.
ag_locales_language_packs_absent: []

# the default locale
ag_default_locale: en_US.UTF-8

# the locale(s) that you want to present.
ag_locales_present:
  - en_US.UTF-8

# the locale(s) that you want to absent.
ag_locales_absent: []
```

If you need the locale(s) more customized, you can take a look in templates/etc/default/locale.j2 file. There are other vars.

Dependencies
------------

None.

Example Playbook
----------------
```yaml
    - hosts: servers
      roles:
         - { role: adriagalin.locales }
```

ToDo
-------
- Add Debian path for locale.

License
-------

GPLv3 License.

Author Information
------------------

[Adrià Galín](http://www.adriagalin.com)

Inspiration
------------------

During development, some roles in Ansible Galaxy/Github also inspired me:

  - [michaelrigart](https://github.com/michaelrigart/ansible-role-motd)
  - [knopki](https://github.com/knopki/ansible-locale)
  - [tersmitten](https://github.com/Oefenweb/ansible-locales)
  - [nickjj](https://github.com/nickjj/ansible-locale)
  - and many others.

  thank you.

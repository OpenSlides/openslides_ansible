OpenSlides
==========

Presentation and assembly system http://openslides.org

This role installs OpenSlides in "Big Mode". The "Big Mode" is only supported
in OpenSlides >= 2.1 which is not released yet. There fore you have to Install
OpenSlides from git by setting the ansible variable ```openslides_use_git``` to
```true```.

Requirements
------------

Currently this role only supports Ubuntu 16.04 and Archlinux.


Role Variables
--------------

```yaml
# You have to set this to a random string. Do not share it.
openslides_secure_key: false

# The number of worker which should be started. CPU + 1 workers is advised.
openslides_worker_count: 2

# If set to true, the global nginx config is rewritten to listen on all hosts.
openslides_nginx_global: false

# Creates a virtual host which listens to the given names. This is ignored if
# openslides_nginx_global is set to true.
openslides_nginx_domains: []

# If set to False the stable version of openslides is installed from pypi. If set
# to True, then the development version or another git version is used.
openslides_use_git: false
```


Example Playbook
----------------

Install openslides from git
```yml
    - hosts: servers
      roles:
         - { role: openslides, openslides_secure_key: RandomString, openslides_use_git: true }
```


License
-------

MIT


Author Information
------------------

Oskar Hahn <mail@oshahn.de>

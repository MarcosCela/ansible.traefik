ansible.traefik
=========
[![pipeline status](https://gitlab.com/Marcos.Cela/ansible-traefik/badges/master/pipeline.svg)](https://gitlab.com/Marcos.Cela/ansible-traefik/pipelines)
[![MIT license](https://img.shields.io/static/v1.svg?label=license&message=MIT&color=blue&style=flat-square)](https://opensource.org/licenses/MIT)

------------
Set up [Traefik] with docker backend and automatic SSL/TLS certificates via [Let's Encrypt].

Requirements
------------

You need a target machine with:
- Docker

If you want to use Docker, there are very useful roles to install it:

- [geerlingguy.docker]: Also known as the "Ansible guy", he has a lot of very
  useful Ansible roles.


Role Variables
--------------
The role requires the following variables, and will fail if they are not set:

- ***acme_email***: We are using [Let's Encrypt] certificates, and you require an email
  where you will receive notifications about the status of your certificates, like
  certificates close to their expiration date. Example: ***my@mail.org***.


Example Playbook
----------------

```yaml
- hosts: proxy
  roles:
     - role: ansible-traefik
       acme_email: my@mail.org
```

License
-------

MIT




[geerlingguy.docker]: https://github.com/geerlingguy/ansible-role-docker
[Traefik]: https://traefik.io/
[Let's Encrypt]: https://letsencrypt.org/
ansible.traefik
=========

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

- ***docker_domain***: Is the  base domain used for frontend rules. If you are going
  to use [Traefik] to expose a public URL, you can use your domain here. An example for
  this variable is ***myorganization.org***. You can also override this variable with labels
  for specific frontends.
- ***acme_email***: We are using [Let's Encrypt] certificates, and you require an email
  where you will receive notifications about the status of your certificates, like
  certificates close to their expiration date. Example: ***my@mail.org***.


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: proxy
      roles:
         - role: ansible-traefik
           acme_email: my@mail.org
           docker_domain: myorganization.org
           

License
-------

MIT




[geerlingguy.docker]: https://github.com/geerlingguy/ansible-role-docker
[Traefik]: https://traefik.io/
[Let's Encrypt]: https://letsencrypt.org/
Acme-Tiny Setup
===============

This is an ansible role for setting up ACME and everything that is required for Let's encrypt. It is highly influenced by this role: ganto.acme\_tiny. Many thanks [ganto](https://linuxmonk.ch/)!

Why we do not use one of the existing roles?

* For the first reason read the section "Promise" below. We need something reliable.
* This role will be used by [maestro](https://github.com/inofix/maestro) and must follow the logic used there. (Of course, the role can be used without maestro..)

Promise
-------

Sure this role may change in the future, but we will only expand features to not break backwards compatibility.

If radical changes should become necessary, a new role will be created, probably with an 'ng' or version suffix...

Installation
------------

 # ansible-galaxy install zwischenloesung.acme-tiny-setup

Requirements
------------

* Ansible >2.0
* Python2/3 on target host
* Generic UNIX with FHS
* Sudo
* Systemd (per default)

Role Variables
--------------

* app\_\_acme\_\_tiny\_\_user - optional, default='acme'
* app\_\_acme\_\_tiny\_\_group - optional, default='acme'
* app\_\_acme\_\_tiny\_\_home - optional, default='/var/lib/acme'
* app\_\_acme\_\_tiny\_\_config\_dir - optional, default='/etc/ssl/acme-tiny'
* app\_\_acme\_\_tiny\_\_openssl\_config - optional, default='/etc/ssl/openssl.cnf'
* app\_\_acme\_\_tiny\_\_challenge\_dir - optional, default='/var/www/acme-challenges'
* app\_\_acme\_\_tiny\_\_account\_key - optional, default='account.key'
* app\_\_acme\_\_tiny\_\_domain - optional, default='example.com'
* app\_\_acme\_\_tiny\_\_cert\_name - optional, auto
* app\_\_acme\_\_tiny\_\_log\_dir - optional, default='/var/log/acme-tiny'
* app\_\_acme\_\_tiny\_\_cert\_dir - optional, auto
* app\_\_acme\_\_tiny\_\_key - optional, auto
* app\_\_acme\_\_tiny\_\_request - optional, auto
* app\_\_acme\_\_tiny\_\_letsencrypt\_certs - optional, default=[ {url='https://letsencrypt.org/certs/lets-encrypt-x3-cross-signed.pem', file='intermediate.crt'}, {url='https://letsencrypt.org/certs/isrgrootx1.pem', file='ca.crt'} ]
* app\_\_acme\_\_tiny\_\_key\_length - optional, default=4096

Dependencies
------------

Example Playbook
----------------

    - hosts: servers
      roles:
         - zwischenloesung.acme-tiny-setup

License
-------

GPLv3

Author Information
------------------

* Michael Lustenberger at [inofix.ch](http://www.inofix.ch)

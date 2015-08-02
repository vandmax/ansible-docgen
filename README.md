ansible-docgen
=====================

Description
===========

ansible-docgen generates documentation from annotated Ansible Playbooks and Roles

[![alt text](https://secure.travis-ci.org/starboarder2001/ansible-docgen.png?branch=master "ansible-docs latest build")](http://travis-ci.org/starboarder2001/ansible-docgen)
[![alt text](https://img.shields.io/pypi/v/ansible-docgen.svg "ansible-docs PyPI version")](https://pypi.python.org/pypi/ansible-docgen)
[![alt text](https://img.shields.io/pypi/dm/ansible-docgen.svg "ansible-docs PyPI downloads")](https://pypi.python.org/pypi/ansible-docgen)


Installation
===========

```shell
pip install ansible-docgen
```

or

```shell
easy_install ansible-docgen
```

Usage
===========

### Annotate Your Playbooks and Roles
```yaml
---
# test_playbook.yml
# Author: John Doe
# Description: Install a Webserver
- name: Install Apache
  yum: name=httpd state=installed
```
```yaml
---
# roles/appserver/tasks/main.yml
# Author: John Doe
# Description: Appserver role
- name: Copy Installer
  copy: src=installer dest=/tmp/
- name:  Run Installer
  shell: /tmp/installer.sh
```
### Generate Markup Files from Annotation
##### Use -p to specify your project directory. Click the links to preview the Markup generated by ansible-docgen.

`ansible-docgen -p your_ansible_project`

`Generated Markup File` [your_ansible_project/otherroles/README.md](test/integration/otherroles/README.md)

`Generated Markup File` [your_ansible_project/roles/README.md](test/integration/roles/README.md)

`Generated Markup File` [your_ansible_project/README.md](test/integration/README.md)


##### If your current directory is your project directory just run the ansible-docgen without any arguments.
Click the links to preview the Markup generated by ansible-docgen.

`cd your_ansible_project && ansible-docgen`

`Generated Markup File` [otherroles/README.md](test/integration/otherroles/README.md)

`Generated Markup File` [roles/README.md](test/integration/roles/README.md)

`Generated Markup File` [README.md](test/integration/README.md)

License
=======

ansible-docgen is released under the MIT License.

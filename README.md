Docker EE Engine
================

A playbook to install and configure Docker's Commercially Supported release of
Docker Engine.

Requirements
------------

Access to the internet. The playbook will reach out to
<https://storebits.docker.com/>.

Role Variables
--------------

| Parameter            | Required | Default  | Description                                               |
| -------------------- | -------- | -------- | --------------------------------------------------------- |
| docker_repo          | no       | main     | The repo to install EE Engine from (stable-17.03, etc)    |
| docker_engine_labels | no       |          | A map of labels for this engine                           |
| docker_bind_socket   | no       | true     | Should the engine bind to the Docker socket               |
| docker_bind_ip       | no       |          | Should the engine bind to an ip address                   |
| docker_port          | no       | 2375     | IP port the engine should bind to                         |

Dependencies
------------

None

Example Playbook
----------------

Simple example that includes a couple of labels.

``` yaml
- hosts: all
  become: true
  vars:
    docker_engine_labels:
      storage: ssd
      location: rack1
  roles:
    - ee_engine
```

License
-------

Apache 2.0

Author Information
------------------

Chad Metcalf <mailto:metcalfc@gmail.com>

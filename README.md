latex
=====

Ansible role to output configuration formatted as [LaTeX](https://www.latex-project.org/).

Requirements
------------

* [ansible.builtin](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/index.html)
* [ansible.posix](https://docs.ansible.com/ansible/latest/collections/ansible/posix/index.html)
* [community.general](https://docs.ansible.com/ansible/latest/collections/community/general/)
* [community.docker](https://docs.ansible.com/ansible/latest/collections/community/docker/index.html)

Role Variables
--------------

* defaults

  * `main.yaml`

    ```yaml
    latex_vmware_cluster:
      caption: vmware-cluster

    latex_vmware_datastore:
      caption: vmware-datastore

    latex_vmware_adapter:
      caption: vmware-adapter

    latex_vmware_guest_network:
      caption: vmware-guest-network

    latex_vmware_guest_hardware:
      caption: vmware-guest-hardware


    latex_system_group:
      caption: system-group

    latex_system_user:
      caption: system-user

    latex_system_sudo:
      caption: system-sudo

    latex_system_filesystem:
      caption: system-filesystem

    latex_system_logrotate:
      caption: system-logrotate

    latex_system_software:
      caption: system-software


    latex_ceph_metadata_mon:
      caption: ceph-metadata-mon

    latex_ceph_metadata_osd:
      caption: ceph-metadata-osd

    latex_ceph_metadata_mds:
      caption: ceph-metadata-mds

    latex_ceph_metadata_mgr:
      caption: ceph-metadata-mgr

    latex_ceph_dump_config:
      caption: ceph-dump-config

    latex_ceph_dump_daemon:
      caption: ceph-dump-daemon
      daemons:
        - alertmanager
        - node-exporter
        - prometheus
        - grafana

    latex_ceph_dump_osd:
      caption: ceph-dump-osd

    latex_ceph_dump_pool:
      caption: ceph-dump-pool


    latex_docker_stack:
      caption: docker-stack

    latex_docker_stack_task:
      caption: docker-stack-task

    latex_docker_service:
      caption: docker-service

    latex_docker_host:
      caption: docker-host


    latex_portainer_user:
      caption: portainer-user

    latex_portainer_tag:
      caption: portainer-tag

    latex_portainer_endpoint:
      caption: portainer-endpoint

    latex_portainer_endpoint_group:
      caption: portainer-endpoint_group
    ```

* vars

  ```yaml
  latex_docker_service_query: ""  # internally used query
  ```

Dependencies
------------

* [software](https://github.com/mario-slowinski/software)
* [ceph](https://github.com/mario-slowinski/ceph)
* [porainer](https://github.com/mario-slowinski/porainer)

Tags
----

* latex.vmware
  * latex.vmware.guest
    * latex.vmware.guest.hardware
    * latex.vmware.guest.network
  * latex.vmware.cluster
  * latex.vmware.datastore
  * latex.vmware.adapter
* latex.system
  * latex.system.group
  * latex.system.user
  * latex.system.sudo
  * latex.system.filesystem
  * latex.system.logrotate
  * latex.system.software
* latex.docker
  * latex.docker.service
  * latex.docker.host
  * latex.docker.stack
* latex.ceph
  * latex.ceph.dump
    * latex.ceph.dump.config
    * latex.ceph.dump.pool
    * latex.ceph.dump.osd
  * latex.ceph.metadata
    * latex.ceph.metadata.mon
    * latex.ceph.metadata.osd
    * latex.ceph.metadata.mds
    * latex.ceph.metadata.mgr
* latex.portainer
  * latex.portainer.user
  * latex.portainer.group
  * latex.portainer.tag
  * latex.portainer.endpoint
  * latex.portainer.endpoint_group

Examples
--------

* `requirements.yaml`

  ```yaml
  - name: latex
    src: https://github.com/mario-slowinski/latex
  ```

* `playbook.yaml`

  ```yaml
  - hosts: servers
    gather_facts: true
    roles:
      - role: latex
  ```

License
-------

[GPL-3.0](https://www.gnu.org/licenses/gpl-3.0.html)

Author Information
------------------

[mario.slowinski@gmail.com](mailto:mario.slowinski@gmail.com)

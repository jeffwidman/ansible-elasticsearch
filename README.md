Elasticsearch Ansible role
=========

This is an Ansible role that installs and configures Elasticsearch.

The role includes optional Xenforo scripts for Elasticsearch, although by default they
are not installed. These scripts are only useful if you have the Enhanced Search
addon for Xenforo.

Role Variables
--------------

For the standard ES variables, see defaults/main.yml. You will likely want to
increase `es_heap_size` as it defaults to an insanely low 256mb for safety.

To install the Xenforo scripts for Elasticsearch, set `xenforo` to `True`. A
good rule of thumb is ~90MB of `es_heap_size` per 1 million Xenforo forum posts
with a minimum of 256MB, per https://xenforo.com/community/threads/scaling-database.98161/#post-945458

Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: elasticsearch,
              xenforo: True,
              es_heap_size: 500m,
              tags: ['es'] }

License
-------

MIT

Author Information
------------------

Jeff Widman jeff@jeffwidman.com

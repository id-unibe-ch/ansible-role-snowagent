snowagent
=========

Installs and configured Unibe snowagent agent for software asset management (SAM).

TODO
----

- [ ] Add exlude paths in template

Requirements
------------

No prerequisites necessary at the moment.


Role Variables
--------------

See the file [defaults/main.yml](defaults/main.yml) for a list of the current supported variables.

Example Playbook
----------------

Reference this role in your playbook:

```yaml
---
- name: Example playbook
  hosts: "all"
  roles:
    - role: unibeid.snowagent
      become: true
```

License
-------

MIT

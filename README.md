ansible_role_localbin
=====================

A small role that manages /usr/local/bin scripts.

Requirements
------------

None.

Role Variables
--------------

| Name                  | Explanation                                        |
|-----------------------|----------------------------------------------------|
| `local_bin_templates` | List of profile templates to add to /usr/local/bin |

Each template should be written like this:

```yml
local_bin_templates:
  - template: example_script.j2
    owner: root
    group: root
    mode: 0555
```

Defaults for owner, group and mode are `root`, `root` and `555` respectively.

Example Playbook
----------------

```yml
- hosts: servers
  roles:
    - role: ansible_role_localbin
      vars:
        local_bin_templates:
          - template: example_script.j2
```

License
-------

MIT

Author Information
------------------

Simo Tuomisto, Aalto University 2024

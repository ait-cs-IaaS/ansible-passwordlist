Passwordlist
============

This ansible-role places a password list into a specific directory. It is possible to replace certain passwords inside the list via variables.

Requirements
------------

- `>= ansible 2.10`

Role Variables
--------------

```yaml
passwordlist_srcfile: rockyou.tar.gz
passwordlist_destfile: 'rockyou.txt'
passwordlist_destdir: '/var/www/html'
passwordlist_replace:
  - src: '^abc123$'
    dest: 'AMINERWASHERE'
```

Dependencies
------------

This role has no dependencies.

Example Playbook
----------------

```yaml
    - hosts: localhost
      become: yes
      roles:
         - role: passwordlist
           vars:
             passwordlist_destdir: '/home/ubuntu/'
             passwordlist_replace:
               - src: '^12345'
                 dest: 'CRACK_THIS_PASS'
           tags: wordlist
```

License
-------

GPL-3

Author Information
------------------

Wolfgang Hotwagner(https://www.ait.ac.at)

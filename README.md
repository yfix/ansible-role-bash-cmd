# ansible-role bash-cmd

Will execute the passed `command` in the passed `dir`. Useful for doing things like bundle install and rake db:migrate via a role.

```yml
- hosts: defaults
  roles:
    - { role: bash_cmd, dir: '/var/www/my_app', cmd: 'bundle install' }
    - { role: bash_cmd, dir: '/var/www/my_app', cmd: 'bundle exec rake db:migrate' }
```

Additionally you can specify the role to only run on a single node. Useful for things that would cause errors if run on multiple hosts.

```yml
- hosts: defaults
  roles:
    - { role: bash_cmd, dir: '/var/www/my_app', cmd: 'bundle install' }
    - { role: bash_cmd, dir: '/var/www/my_app', cmd: 'bundle exec rake db:migrate', single_node: true }
```

## License

* MIT

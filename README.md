# Rbenv

  Ansible role for installing [rbenv](https://github.com/sstephenson/rbenv) and manage multiple ruby versions.

  You can use this role for install a customized version of ruby system-wide or per user, and install a curated list of
  gemsets.

## Requirements

  None.

## Role Variables

### `rbenv_env`

  Used to select the install type: `system` or `user`. If you select `user` install, you have to specify the users that
  will be installed in. By default, environent is `system`.

### `rbenv_ruby_version`

  Version of ruby to install as global `rbenv` ruby

### `rbenv_with_patch`

  If you need to patch ruby before compile it, put the URL taht point to patch file here to apply it.

### `rbenv_users`

  A list of usernames to install rbenv locally. Used in conjunction with `rbenv_env`.

### `rbenv_uninstall versions`

  A list of ruby versions to uninstall. Use it to remove old versions.



Example:

    - hosts: web
      roles:
        - role: rbenv
          rbenv_env: user
          rbenv_ruby_version: 2.0.0-p353
          rbenv_users:
            - mmacia

## Dependencies

  None.

## License

  MIT

## Author Information

Moisés Maciá <mmacia@gmail.com>

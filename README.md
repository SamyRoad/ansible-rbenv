Rbenv
========

Role for installing [rbenv](https://github.com/sstephenson/rbenv).

Requirements
------------

none

Role Variables
--------------

Default variables are:

    rbenv:
      env: system
      version: v0.4.0
      ruby_version: 2.1.5

    rbenv_repo: "git://github.com/sstephenson/rbenv.git"
    rbenv_with_patch: ''

    rbenv_plugins:
      - { name: "rbenv-vars",
          repo: "git://github.com/sstephenson/rbenv-vars.git",
          version: "v1.2.0" }

      - { name: "ruby-build",
          repo: "git://github.com/sstephenson/ruby-build.git",
          version: "v20150506" }

      - { name: "rbenv-default-gems",
          repo: "git://github.com/sstephenson/rbenv-default-gems.git",
          version: "ead67889c91c53ad967f85f5a89d986fdb98f6fb" }

      - { name: "rbenv-installer",
          repo: "git://github.com/fesplugas/rbenv-installer.git",
          version: "22cc96aa45d06faca5958b1aa1688596198407a3" }

      - { name: "rbenv-update",
          repo: "git://github.com/rkh/rbenv-update.git",
          version: "bf757453498337807a46e24074d29173f1a8abec" }

      - { name: "rbenv-whatis",
          repo: "git://github.com/rkh/rbenv-whatis.git",
          version: "v1.0.0" }

      - { name: "rbenv-use",
          repo: "git://github.com/rkh/rbenv-use.git",
          version: "v1.0.0" }

    rbenv_users: []

Description:

- ` rbenv.env ` - Type of rbenv installation. Allows 'system' or 'user' values
- ` rbenv.version ` - Version of rbenv to install (tag from [rbenv releases page](https://github.com/sstephenson/rbenv/releases))
- ` rbenv.ruby_version ` - Version of ruby to install as global rbenv ruby
- ` rbenv_repo ` - Repository with source code of rbenv to install
- ` rbenv_with_patch ` - Url to patch file that will be applied before install ruby.
- ` rbenv_plugins ` - Array of Hashes with information about plugins to install
- ` rbenv_users ` - Array of usernames for multiuser install. User must be present in the system

Example:

    - hosts: web
      vars:
        rbenv_env: user
        rbenv_ruby_version: 2.0.0-p353
      roles:
        - role: rbenv
          rbenv_users:
            - mmacia

Dependencies
------------

- build

License
-------

MIT

Author Information
------------------

Moisés Maciá <mmacia@gmail.com>

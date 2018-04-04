Ansible role cron
=========

Ansible role for managing crontab entries and managing cron service

Requirements
------------

None

Role Variables
--------------

##### `cron_entries` (required)

Specifies crontab entries as a dict. Example below should be clear.
If cron_file is not defined, user's crontab is used instead.
Default value `*` is used for month, weekday, day, or hour and value `0` is for minute if variables are not defined.

```
cron_entries:
  - name: script_name_goes_here
    user: script_user
    cron_file: my_cron_entry
    command: /bin/true
    month: "*"
    weekday: "*"
    day: "*"
    hour: "0"
    minute: "0"
    entry_state: present
```
##### `cron_default_month/cron_default_weekday/cron_default_day/cron_default_hour` (optional)

Default value is `*`.

##### `cron_default_minute` (optional)

Default value `0`

##### `cron_default_entry_state` (optional)

Defines if entry should be present or absent. Default is present.

##### `cron_state` (optional)

Defines if cron service is started. Default is started.

##### `cron_enabled` (optional)

Defines if cron service is enabled (started automatically during boot).



Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
         - { role: cron, tags: cron}

License
-------

MIT


Author Information
------------------

Tuomas Vallaskangas tvallas@iki.fi

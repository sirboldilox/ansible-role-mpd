Ansible MPD
===========

[![Ansible Galaxy](http://img.shields.io/badge/ansible--galaxy-mpd-blue.svg)](https://galaxy.ansible.com/list#/roles/6633)

An Ansible role to manage [MPD](http://musicpd.org) on debian systems.

- Installs mpd and mpc.
- Configures mpd.

Default variables
---------

```yaml
# Default settings for mpd

# Files and directories
mpd_music_directory:    "/var/lib/mpd/music"
mpd_playlist_directory: "/var/lib/mpd/playlists"
mpd_db_file:            "/var/lib/mpd/tag_cache"
mpd_state_file:         "/var/lib/mpd/state"
mpd_sticker_file:       "/var/lib/mpd/sticker.sql"
mpd_log_file:           "/var/log/mpd/mpd.log"
mpd_pid_file:           "/run/mpd/pid"

# General music daemon options
mpd_user:               "mpd"
mpd_group:              "audio"

# Audio devices (Default Null device)
mpd_audio_devices: 
  - name:   "Auto Null Output"
    type:   "null"
```

Example Playbook
----------------

Basic playbook with pulse audio backend

```yaml
- hosts: all

  roles:
     sirboldilox.mpd:

  vars:
    - mpd_music_directory: "/media/music"
    - mpd_audio_device:
        - name: "Pulse Audio"
        - type: "pulse"
```

License
-------

MIT

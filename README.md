[![Ansible Galaxy](https://raw.githubusercontent.com/roles-ansible/role-grafana-kiosk/master/.github/galaxy.svg?sanitize=true)](https://galaxy.ansible.com/do1jlr/grafana_kiosk)
[![Build Status](https://travis-ci.org/roles-ansible/role-grafana-kiosk.svg?branch=master)](https://travis-ci.org/roles-ansible/role-grafana-kiosk)
[![MIT License](https://raw.githubusercontent.com/roles-ansible/role-grafana-kiosk/master/.github/license.svg?sanitize=true)](https://github.com/roles-ansible/role-grafana-kiosk/blob/master/LICENSE)
[![Ansible Lint check](https://github.com/roles-ansible/role-grafana-kiosk/workflows/Ansible%20Lint%20check/badge.svg)](https://github.com/roles-ansible/role-grafana-kiosk/actions?query=workflow%3A%22Ansible+Lint+check%22)
[![Ansible check debian:buster](https://github.com/roles-ansible/role-grafana-kiosk/workflows/Ansible%20check%20debian:buster/badge.svg)](https://github.com/roles-ansible/role-grafana-kiosk/actions?query=workflow%3A%22Ansible+check+debian%3Abuster%22)

 ansible role grafana-kiosk
=============================
Ansible role to deploy the grafana-kiosk from [github.com/grafana/grafana-kiosk](https://github.com/grafana/grafana-kiosk.git).

 example playbook
---------
tbd.

 variables
-----------
Here you find some basic explainations what the variables do.
Remeber that you can find a complete list of variables in the ``defaults`` Folder.

+ User to launch grafana-kiosk *(e.g. ``pi``)*:
```
grafana_kiosk:
  user: "{{ ansible_user }}"
```

+ The grafana-kiosk RELEASE we using:
```
grafana_kiosk:
  git_release: 'v1.0.2'
```

+ The URL where the grafana-kiosk repo is located:
```
grafana_kiosk:
  git_url: 'https://github.com/grafana/grafana-kiosk'
```

+ Should we install the required packages *(like chromium)*:
```
grafana_kiosk:
  install_requirements: true
```

+ The required packages we install:
```
grafana_kiosk:
  required_packages:
    - chromium
    - unclutter
```

+ Install r update the packages? *(use ``latest`` to upgrade packages)*
```
grafana_kiosk:
  install_state: 'present'
```

+ What architecture are you running on? *(Used for downloading the binary)*:
```
grafana_kiosk:
  architecture: 'autodetect'
```

+ Here you can set the config of grafana-kiosk:
```
grafana_kiosk:
  general:
    kiosk_mode: full
    autofit: true
    lxde: true
    lxde_home: "/home/{{ ansible_user }}"
  target:
    login_method: anon
    username: user
    password: changeme
    playlist: false
    URL: https://play.grafana.org
    ignore_certificate_errors: false
```
+ Should we create and enable a systemd job?
```
grafana_kiosk:
  manage_systemd: true
```

+ We need to set the correct DISPLAY varriable!
```
grafana_kiosk:
  display: DISPLAY=:0
```

+ should we enable autologin for lightdm? *(If you are using a raspberry pi, please do this via ``raspi-config``!)*
```
grafana_kiosk:
  lightdm_autologin: false
```

+ perform basic versionscheck? *(recomended to set to true)*
```
submodules_versioncheck: false
```

Role Name
=========

Ce role ansible permet d'installer [Fail2ban](https://github.com/tassyk/security/blob/master/hardening_Fail2ban.md) sur une machine Linux Centos 7.

Pour le moment, seul le jail pour SSH est configuré.
 
Requirements
------------


Role Variables
--------------

Les variables par défaut sont renseignés dans default/main.yml :
```
update_pkg: mise à jour ou non des paquets du système

## Options de configuration personnalisées
costum_config: liste des paramètres 

## SSH Jail
- ban_time: temps de banissment
- ssh_port: port ssh
- ignore_ip: liste d'IP à ignorer
- max_retry: nombre d'échec permis
- log_path: fichier log
```
Dependencies
------------

Le rôle peut être intégré facilement dans d'autres projets. Pour ce faire :
- créer un fichier **requirements.yml** avec le contenu ci-dessous :
```
---
- name : fail2ban
  src : https://github.com/tassyk/ansible-fail2ban.git
  scm: git
  version : origin/master
```
- Installer le rôle avec ansible Galaxy :
```
ansible-galaxy install -r requirements.yml -p /chemin/repertoire/roles
```
Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: localhost
      remote_user: user
      become: True
      roles:
      - ansible-fail2ban

Exemple d'exécution du playbook :
```
ansible-playbook fail2ban.yml -i hosts -u user
```

License
-------

TassyK

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).

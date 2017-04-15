# Mediadrop for YunoHost

[![Latest Version](https://img.shields.io/badge/version-_--_-green.svg?style=flat)](https://github.com/YunoHost-Apps/mediadrop_ynh/releases)
[![Status](https://img.shields.io/badge/status-testing-yellow.svg?style=flat)](https://github.com/YunoHost-Apps/mediadrop_ynh/milestones)
[![Dependencies](https://img.shields.io/badge/dependencies-includes-lightgrey.svg?style=flat)](https://github.com/YunoHost-Apps/mediadrop_ynh#dependencies)
[![GitHub license](https://img.shields.io/badge/license-GPLv3-blue.svg?style=flat)](https://raw.githubusercontent.com/YunoHost-Apps/mediadrop_ynh/master/LICENSE)
[![Yunohost version](https://img.shields.io/badge/yunohost-2.4.2_tested-orange.svg?style=flat)](https://github.com/YunoHost/yunohost)
[![GitHub issues](https://img.shields.io/github/issues/YunoHost-Apps/mediadrop_ynh.svg?style=flat)](https://github.com/YunoHost-Apps/mediadrop_ynh/issues)

## Mediadrop c'est quoi ?

MediaDrop est la solution idéale pour les personnes ou organisations souhaitant diffuser de la vidéo ou de l'audio.

Source: [mediadrop.video](http://mediadrop.video/)

### Installation

`$ sudo yunohost app install https://github.com/YunoHost-Apps/mediadrop_ynh.git`

### Mise à jour

`$ sudo yunohost app upgrade --verbose mediadrop -u https://github.com/YunoHost-Apps/mediadrop_ynh.git`

### Utilisation

Accéder à l'administration du site en écrivant l'adresse suivante dans votre navigateur.

https://www.domain.tld/mediadrop/admin

Le nom d'utilisateur est "*admin*" et le mot de passe "*admin*"

## Fonctionnalité pour MediaDrop

Jouer avec les services

#### Relancer MediaDrop

`sudo systemctl stop mediadrop`
`sudo systemctl start mediadrop`
`sudo systemctl status mediadrop`

#### Relancer uWSGI

`sudo systemctl stop mediadrop.uwsgi`
`sudo systemctl start mediadrop.uwsgi`
`sudo systemctl status mediadrop.uwsgi`

### Problème rencontré

Si vous rencontez cette erreur dans le fichier syslog ? 

`Use 'mysqld --thread_stack=#' to specify a bigger stack.")`

C'est que l'option thread_stack n'est pas assez élevé. Cette option de gérer la taille de la pile pour chaque thread.

Remplacer dans le fichier /etc/mysql/my.cnf

`thread_stack = 128K`

par

`thread_stack = 156K`

Vous pouvez l'ajuster, la documentation mysql dit ceci.

La valeur par défaut de 192 Ko (256 Ko pour les systèmes 64 bits) est suffisamment grande pour un fonctionnement normal. Si la taille de la pile de fil est trop petite, elle limite la complexité des instructions SQL que le serveur peut gérer, la profondeur de récursion des procédures stockées et d'autres actions consommant de la mémoire.

Source: [Documentation MySQL](https://dev.mysql.com/doc/refman/5.7/en/server-system-variables.html#sysvar_thread_stack)

## What is MediaDrop?

MediaDrop provides unparalleled organization, statistics, accessibility, and scalability. Well-designed and well-engineered it is the ideal solution for any organization with large collections of video or audio.

Source: [mediadrop.video](http://mediadrop.video/)

### Use

Access the site administration by writing the following address in your browser.

https://www.domain.tld/mediadrop/admin

User is "*admin*" and password is "*admin*"

## Features for Yunohost app

Play as the service

#### Restart mediadrop

`sudo systemctl stop mediadrop`
`sudo systemctl start mediadrop`
`sudo systemctl status mediadrop`

#### Restart uWSGI

`sudo systemctl stop mediadrop.uwsgi`
`sudo systemctl start mediadrop.uwsgi`
`sudo systemctl status mediadrop.uwsgi`

### Troubleshooting

If you have this error into syslog file ? 

`Use 'mysqld --thread_stack=#' to specify a bigger stack.")`

This is because the thread_stack option is not high enough. This option manages the stack size for each thread.

Replace into this file /etc/mysql/my.cnf

`thread_stack = 128K`

by

`thread_stack = 156K`

You can adjust it, the mysql documentation says this.

The default of 192KB (256KB for 64-bit systems) is large enough for normal operation. If the thread stack size is too small, it limits the complexity of the SQL statements that the server can handle, the recursion depth of stored procedures, and other memory-consuming actions.

Source: [Documentation MySQL](https://dev.mysql.com/doc/refman/5.7/en/server-system-variables.html#sysvar_thread_stack)

### Version 1.0.1 (06/04/17)

- Install work fine

### Version 1.0.0 (13/03/17)

- Create script install

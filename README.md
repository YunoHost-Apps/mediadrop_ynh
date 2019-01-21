# Mediadrop for YunoHost

[![Integration level](https://dash.yunohost.org/integration/mediadrop.svg)](https://dash.yunohost.org/appci/app/mediadrop)  
[![Install Mediadrop with YunoHost](https://install-app.yunohost.org/install-with-yunohost.png)](https://install-app.yunohost.org/?app=mediadrop)

> *This package allow you to install Mediadrop quickly and simply on a YunoHost server.  
If you don't have YunoHost, please see [here](https://yunohost.org/#/install) to know how to install and enjoy it.*

## Overview
MediaDrop provides unparalleled organization, statistics, accessibility, and scalability. Well-designed and well-engineered it is the ideal solution for any organization with large collections of video or audio.

MediaDrop est la solution idéale pour les personnes ou organisations souhaitant diffuser de la vidéo ou de l'audio..

**Shipped version:** 0.10.3

## Screenshots

![](Link to an screenshot for this app)

## Demo

* [Official demo](Link to a demo site for this app)

## Configuration

How to configure this app: by an admin panel, a plain file with SSH, or any other way.

## Documentation

 * Official documentation: Link to the official documentation of this app
 * YunoHost documentation: If specific documentation is needed, feel free to contribute.

## Use

Access the site administration by writing the following address in your browser.

https://www.domain.tld/mediadrop/admin

User is "*admin*" and password is "*admin*"
 
## Utilisation

Accéder à l'administration du site en écrivant l'adresse suivante dans votre navigateur.

https://www.domain.tld/mediadrop/admin

Le nom d'utilisateur est "*admin*" et le mot de passe "*admin*"


## YunoHost specific features

#### Multi-users support

Are LDAP and HTTP auth supported?
Can the app be used by multiple users?

#### Supported architectures

* x86-64b - [![Build Status](https://ci-apps.yunohost.org/ci/logs/mediadrop%20%28Community%29.svg)](https://ci-apps.yunohost.org/ci/apps/mediadrop/)
* ARMv8-A - [![Build Status](https://ci-apps-arm.yunohost.org/ci/logs/mediadrop%20%28Community%29.svg)](https://ci-apps-arm.yunohost.org/ci/apps/mediadrop/)
* Jessie x86-64b - [![Build Status](https://ci-stretch.nohost.me/ci/logs/mediadrop%20%28Community%29.svg)](https://ci-stretch.nohost.me/ci/apps/mediadrop/)

## Limitations

* Any known limitations.

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

## Additional information

* Other information you would add about this application

**More information on the documentation page:**  
https://yunohost.org/packaging_apps

## Links

 * Report a bug: https://github.com/YunoHost-Apps/mediadrop_ynh/issues
 * App website: [mediadrop.video](http://mediadrop.video/)
 * YunoHost website: https://yunohost.org/

---

Developers info
----------------

**Only if you want to use a testing branch for coding, instead of merging directly into master.**
Please do your pull request to the [testing branch](https://github.com/YunoHost-Apps/mediadrop_ynh/tree/testing).

To try the testing branch, please proceed like that.
```
sudo yunohost app install https://github.com/YunoHost-Apps/mediadrop_ynh/tree/testing --debug
or
sudo yunohost app upgrade mediadrop -u https://github.com/YunoHost-Apps/mediadrop_ynh/tree/testing --debug
```

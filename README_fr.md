# Mediadrop pour YunoHost

[![Niveau d'intégration](https://dash.yunohost.org/integration/mediadrop.svg)](https://dash.yunohost.org/appci/app/mediadrop) ![](https://ci-apps.yunohost.org/ci/badges/mediadrop.status.svg) ![](https://ci-apps.yunohost.org/ci/badges/mediadrop.maintain.svg)  
[![Installer Mediadrop avec YunoHost](https://install-app.yunohost.org/install-with-yunohost.svg)](https://install-app.yunohost.org/?app=mediadrop)

*[Read this readme in english.](./README.md)*
*[Lire ce readme en français.](./README_fr.md)*

> *Ce package vous permet d'installer Mediadrop rapidement et simplement sur un serveur YunoHost.
Si vous n'avez pas YunoHost, regardez [ici](https://yunohost.org/#/install) pour savoir comment l'installer et en profiter.*

## Vue d'ensemble

MediaDrop est la solution idéale pour les personnes ou organisations souhaitant diffuser de la vidéo ou de l'audio..


**Version incluse :** 0.10.3~ynh2

**Démo :** https://demo.example.com

## Avertissements / informations importantes

## Utilisation

Accéder à l'administration du site en écrivant l'adresse suivante dans votre navigateur.

https://www.domain.tld/admin

Le nom d'utilisateur est "*admin*" et le mot de passe "*admin*"

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

## Documentations et ressources

* Site officiel de l'app : http://mediadrop.video/
* Documentation officielle de l'admin : https://mediadrop.video/docs/
* Dépôt de code officiel de l'app : https://github.com/mediadrop/mediadrop
* Documentation YunoHost pour cette app : https://yunohost.org/app_mediadrop
* Signaler un bug : https://github.com/YunoHost-Apps/mediadrop_ynh/issues

## Informations pour les développeurs

Merci de faire vos pull request sur la [branche testing](https://github.com/YunoHost-Apps/mediadrop_ynh/tree/testing).

Pour essayer la branche testing, procédez comme suit.
```
sudo yunohost app install https://github.com/YunoHost-Apps/mediadrop_ynh/tree/testing --debug
ou
sudo yunohost app upgrade mediadrop -u https://github.com/YunoHost-Apps/mediadrop_ynh/tree/testing --debug
```

**Plus d'infos sur le packaging d'applications :** https://yunohost.org/packaging_apps
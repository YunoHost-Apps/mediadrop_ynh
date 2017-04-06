# Mediadrop for YunoHost

:warning: Application testing :warning:

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

## Features for Yunohost app

Jouer avec les services

#### Relancer mediadrop

`sudo systemctl stop mediadrop`
`sudo systemctl start mediadrop`
`sudo systemctl status mediadrop`

#### Relancer uWSGI

`sudo systemctl stop mediadrop.uwsgi`
`sudo systemctl start mediadrop.uwsgi`
`sudo systemctl status mediadrop.uwsgi`

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

### Version 1.0.1 (06/04/17)

- Install work fine

### Version 1.0.0 (13/03/17)

- Create script install

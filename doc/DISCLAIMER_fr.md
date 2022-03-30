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

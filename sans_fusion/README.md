ssh-keygen -t rsa

cp ~/.ssh/id_rsa.pub cle_publique

vagrant up

ansible-playbook -i inventory play.yml

### TP 0 :

 * Ajouter un certificat SSL autosigné pour la connexion nginx / client web

Pour Ngnix on a le SSL sur https://192.168.33.18:9000/

Le SSL ce fait dans /roles/nginx/tasks/main.yml et /roles/nginx/templates/lb.j2

 * Ajouter un moteur de base de données Mariadb/Mysql + des utilisateurs/mot de passe, définie dans une liste

Cette partie ne fonctionne pas avec le paquet python pymysql ou python-mysql.
J'ai aussi essayer avec ces 2 modules différent.

* https://docs.ansible.com/ansible/2.9/modules/mysql_user_module.html

En community
* https://docs.ansible.com/ansible/latest/collections/community/mysql/mysql_user_module.html


Mais ça ne fonctionne toujours pas (erreur_mysql.png).
J'ai mis ma partie MySQL qui ne fonctionne pas en commentaire.

La création des users ce fait dans /roles/nginx/tasks/main.yml
La liste des users mysql ce trouve dans /roles/nginx/defaults/main.yml

 * Ajouter un role commun pour les deux groupes de machine pour installer une liste de package prédéfinie (exemple : nmon, htop, tmux, screen)

La liste des packages dans le role commun qui vont êtres installer sont dans /roles/commun/tasks/main.yml

## Pour tous : question bonus (à rendre dans un autre répertoire )

- Fusionner tous les roles dans un seul et unique role : avec le même résultat

La fusion des rôles en un seul rôle ce fait dans le /roles/fusion

SSL:
* /roles/fusion/tasks/nginx.yml
* /roles/fusion/templates/lb.j2

mysql:
* /roles/fusion/tasks/nginx.yml
* /roles/fusion/defaults.yml

Rôle commun:
* /roles/fusion/tasks/commun.yml

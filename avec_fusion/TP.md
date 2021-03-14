## Mode d'emploi

 * Copier votre cle publique dans ./cle_publique
 * commande : vagrant up
 * premier déploiement : ansible-playbook -i inventory play.yml

Suivant le numéro de TP affecté (voir mon mail ) :

### TP 0 :

 * Ajouter un certificat SSL autosigné pour la connexion nginx / client web
 * Ajouter un moteur de base de données Mariadb/Mysql + des utilisateurs/mot de passe, définie dans une liste
 * Ajouter un role commun pour les deux groupes de machine pour installer une liste de package prédéfinie (exemple : nmon, htop, tmux, screen)

### TP 1 :

 * Basculer le restart d'apache2 et nginx dans un handler
 * Ajouter php à apache dans le role apache et insérer une page de test phpinfo() par défaut.
 * Ajouter des regles iptables sur le nginx et apache pour n'accepter qu'une liste de ports définie

## Pour tous : question bonus (à rendre dans un autre répertoire )

- Fusionner tous les roles dans un seul et unique role : avec le même résultat


## Quelques rappels
 * Pour tester le fonctionnement du loadbalancer : http://192.168.33.18:9000 (et plein de F5 pour basculer d'un apache à l'autre et sauf ceux qui passeront en ssl évidemment)

 * Je ferais avec vos dépots la même chose que le mode d'emploi => Je vous conseille donc de rejouer pour être sur que ça fonctionnera. Déjà, vous perdez des points et en plus, vous agacez le correcteur ( aka moi )

 * Ne pas utiliser les modules "command" ou "shell" , sauf extreme urgence. Normalement, vous n'en avez pas besoin.

 * Je préfère une livraison de code via un git (gitlab de préférence) qu'un zip par mail ...

 * n'hésitez pas à rajouter un petit README si vous voyez la necessité #JaimeLaDoc

 * j'espère que vous avez lu les rappels.

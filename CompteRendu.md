# Exercice 2
## Manual

1. Which permet de trouver le chemin d'accès de la/les commandes passées en paramètres

2. On peut chercher un terme dans le manuel en tapant /xxxx puis entrer (xxxx = terme à rechercher)

3. On peut quitter le manuel en appuyant sur la touche q

4. 


## Navigation

Pour se déplacer dans les fichiers, on utilise la commande cd suivie du chemin vers le fichier qui nous intéresse `cd /var/log`
On peut aussi utiliser des chemins relatifs comme `cd ..` pour revenir au répertoire mère, ou `cd -` pour revenir au répértoire précédent
Il est possible de retourner dans son répertoire personnel en tapant juste `cd`

L'accès au dossier root n'est pas autorisé si l'on est pas administrateur, et cd n'est pas reconnue en root, car sudo ne fonctionne que sur les exécutables, pas sur les commandes builtin

Quand on essaye de supprimer un fichier sans indiquer son chemin, le terminal ne le trouve pas, et rm ne peut pas supprimer un dossier
la commande pour supprimer un dossier vide est `rmdir [nom du dossier]` ou `rm -d [nom du dossier]`
pour supprimer un dossier et son contenu il faut utiliser `rm -r`

Il faut donc utiliser `rm /Dossier1/Fichier1` puis `rm -r Dossier1`


## Commandes importantes

`date +"%H:%M:%S"` permet d'afficher l'heure et la commande `Time` lance une commande et analyse les ressources utilisées par cette commande

Les fichiers qui commencent par . sont des fichiers cachés, qui ne s'affiche que si on le demande

ls est située dans /usr/bin/ls

`ll` est une autre version de la commande `ls -alF`

`ls /bin` permet d'afficher les fichiers contenus dans bin

`ls ..` liste les fichiers contenus dans le répertoire mère

`pwd` donne le chemin vers le dossier courant

`echo 'bip' > plop` envoie le résultat de echo dans plop, en écrasant les précédentes données
`echo 'bip' >> plop` envoie le résultat de echo dans plop, à la suite des pécédentes données

`sleep 10 | echo 'toto'` envoie toto sur la sortie standard

`file [nom de fichier]` donne le type du fichier spécifié

`ln [Nom du fichier1][Nom du fichier2]` crée un lien vers un fichier, et la modification du fichier original est répercutée sur le lien, la suppression n'impacte que le fichier original
`ln -s [Nom du fichier1][Nom du fichier2]` crée un lien entre deux fichiers, chaque modification s'applique sur l'autre fichier, et la suppression les supprime tous les deux

CTRL+S permet de mettre en pause le défilement et CTRL+D le remet en route

`head -n 5 /var/log/syslog` permet d'affihcer les 5 premières lignes de syslog
`tail -n 15 /var/log/syslog` permet d'afficher les 15 dernières lignes de syslog
`head -n +10 | tail -n 10 /var/log/syslog` permet d'afficher les lignes 10 à 20 de syslog 

dmesg affiche tous les messages du kernel, et less permet de naviguer de façon plus pratique dans les messages

/etc/passwd contient les infos des utilisateurs pouvant se connecter sur le système, `man 5 passwd` permet d'afficher son manuel

`cut -d: -f1 /etc/passwd` permet de n'afficher que la première colonne de chaque ligne dans /etc/passwd

`wc -l /etc/passwd` permet de connaitre le nombre de lignes dans le fichier, et donc le nombre d'utilisateurs sur la machine

`find / -name passwd` permet de chercher tous les fichiers s'appelant passwd dans la machine

`find / -name passwd > ~/list_passwd_files.txt 2> /dev/null` permet de rediriger le resultat dans list_passwd_files.txt et les erreurs dans /dev/null

`locate history.log` donne le chemin vers history.log /var/log/apt/history.log

Le fichier n'apparait pas dans locate car locate utilise une base de donnée mise à jour à intervalle fixe, et elle ne s'est pas encore mise à jour

# Exercice 3



# Exercice 4

`[\033[\01;35m][\t][\033[00m\][\033[\01;35m]\u@\h\[\033[00m\][\033[\01;36m]\w[\033[00m\]` permet de mettre l'heure en violet, puis l'utilisateur et l'hôte en vert et le chemin courant en bleu

# Exercice 5

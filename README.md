# My Habits Tracker (A Buggy Web Application)

# Présentation du projet

MyHabitTracker est une application web conçu sur une architecture MVC et qui s'inspire de l'arborsence et du fonctionnement du framework Symfony.

Celle-ci est destiné à être utilisée à des fins pédgogique uniquement et dans le cadre de la sensibilisation aux failles de sécurités les plus courantes sur le web.

## Téchnologies

- PHP 8.3
- MySQL 5.7

## Objectifs

Les objectifs sont les suivants :

* Prendre connaissance du code existant
* Paramétrer votre environnement dans le fichier .env ou .env.local
* 1ère partie (3h)
* * Préparer le déploiement de l'application (sur votre machine Debian) en rédigeant votre procédure dans le fichier `doc/DEPLOY.md`
  * Répondez aux questions figurant dans le fichier `doc/QUESTIONS.md`
* 2ème partie (2h)
  * Corriger toutes les failles de sécurité/bugs (voir `doc/TODO.md`) et déployez un correctif (toutes les failles ne sont pas répértoriées)
  * Pensez à mettre à jour le fichier `CHANGELOG.md`

## Lancement du projet

### Création de la base de données

```
php bin/create-database
```

### Lancement du serveur

Pour lancer le projet, vous devez impérativement passer par la commande : `php bin/serve`

### Création de la base de données

Pour créer la base de données vous pouvez lancer la commande : `php bin/create-database `

Un compte admin et utilisateurs seront également créés *(vous trouverez les informations dans le script database.sql)*

Ensuite, vous pouvez alimenter la base de données avec des données démo en lançant la commande : `php bin/load-demo-data`

## Livrables

Le code doit impérativement être push sur le repo GitHub Classroom qui vous a été assigné et sur la branche principale `main`

**!!! ATTENTION : la partie 2 ne sera pas évaluée si ce n'est pas le cas !!!**

# BONNE CHANCE



S’assurer de la connexion SSH : ssh root@[adresse ip]

Récupérer le projet sur le repo git (git clone)

Dans le terminal du projet :

php bin/serve pour lancer l’app en local

composer install --optimize-autoloader (Toujours vérifier si les dépendances sont installées)

créer le .env et copier le contenue du .env.sample

Initialiser git-cliff
wget "https://github.com/orhun/git-cliff/releases/download/v2.10.1/git-cliff-2.10.1-x86_64-unknown-linux-gnu.tar.gz"
tar -tzf git-cliff-2.10.1-x86_64-unknown-linux-gnu.tar.gz

git-cliff --init
git add .
git  commit -m “Doc: first commit”
git-cliff --bump -o .\CHANGELOG.md
commit de version
git tag (numero de version)


INSTALLER AaPanel:
Se connecter en ssh: ssh root@[adresseip]

URL=https://www.aapanel.com/script/install_7.0_en.sh && if [ -f /usr/bin/curl ];then curl -ksSO "$URL" ;else wget --no-check-certificate -O install_7.0_en.sh "$URL";fi;bash install_7.0_en.sh aapanel


(si l’install a besoin d’etre en root faire su - )
bt : commande si jamais perte d’identifiant ?

pendant l’installation dire yes

cela va me donner  un login et un mdp et 2 ip il faut noter absolument la deuxième
Dans AaPanel

Une modal s’affiche choisir LNMP
Aller dans l’onglet :
website -> ajouter un site-> rentrer le nom de domaine (ou l’ip local)

ftp create, database Mysql, choisir la version de php 8.1,
On note db name et ftp setting dans le bloc note.
On valide
Une modale apparaît  on peut la fermer



		 Retourner sur debian :
			“On verifie si on a bien 172.16.1.201
			cd / on va a la racine
			ls
			cd www /
ls
wwwroot
ls > 172.16.1.201” optionnel

		>On retourne a la racine:
			cd var
			mkdir depot_git	
			cd depot_git
			git init --bare

			(git tag si on veut regarder le nom du tag )
			Dans Vs code:
dans mon projet
git remote add vps root@172.16.1.201:/var/depot_git
git push -u vps 1.3.0
ensuite on rentre le mot de passe

Dans Debian:
On va creer le script
Aller a la racine cd /
touch deploy.sh
nano deploy.sh
On copie colle ça :
git --work-tree=/www/wwwroot/176.1.16.211 --git-dir=/var/depot_git checkout -f $1

on sauvegarde et on quitte


			Dans vs code
			git push vps 0.1.0
			Dans Debian
bash deploy.sh [numero de version]


bash deploy.sh <numero de version>On retourne sur aaPanel:On retourne sur aaPanel


s’assurer de ça  pour y acceder il faut cliquer sur mon site  mettre le .Env dans file

Ensuite on clique sur l’ip sur la même page
On se rend dans dans side directory
On désactive xss
On clique sur site directory
Mettre le nom de domaine
Ensuite on clique sur composer
On exécute
.env à créer sur le serveur > file > new blank file

Dans le .env ne pas oublier de changer les valeur des variables d’env:


Ensuite résoudre Les erreurs dans le code, il faut faire un commit a chaque erreur:

add .
git commit -m”Fix: nom de l’erreur résolu”

Quand tous les problèmes sont résolu :
git add .
git-cliff --bump -o .\CHANGELOG.md
git commit -m ’numero de version’
git tag <numero de version>
git push vps <nom du tag>
bash deploy.sh 0.1.0

aaPanel Internet Address: https://90.80.241.65:33595/3b606a22
aaPanel Internal Address: https://172.17.4.13:33595/3b606a22
username: ba20vrmm
password: db3d7dd4


db:
user : sql_lang_dfsfr1_local
password: 2b4d45431b14b8


FTP user profile
User: ftp_lang_dfsfr1_local
Password: f04a64e6ebb468
Database user profile
User: sql_lang_dfsfr1_
Password: 2b4d45431b14b8




S’assurer de la connexion SSH : ssh root@172.16.1.211

Récupérer le projet sur le repo git (git clone)

Dans le terminal du projet :

php bin/serve pour lancer l’app en local

composer install --optimize-autoloader (Toujours vérifier si les dépendance sont installées)

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
bash deploy.sh 0.1.0


bash deploy.sh <numero de version>On retourne sur aaPanel:On retourne sur aaPanel


192.168.122.75

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

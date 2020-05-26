Utilisation
===========

Fonctionnalités de base
-----------------------

On accède à la palette de _Package Control_ en pressant les touches
[Ctrl + shift + P] (Win, Linux) ou [cmd + shift + P] (Mac). Toutes les 
commandes de _Package Control_ commencent justemente par _Package Control_, 
donc nous pouvons commencer par saisir "Package" dans la palette (ou simplement "pac").

Parmi l'ensemble des commandes affichées celles qui intéresseront la plupart
des utilisateurs sont : 

    * _Install Package_ :
        Affiche une liste de tous les paquets disponibles à l'installation.
    * _Add Repository_ (Ajouter un dépôt):
        Ajouter un dépôt qui n'est pas inclus dans le canal par défaut. Cela 
        permet aux utilisateurs d'installer et de mettre à jour 
        automatiquement les paquets de GitHub et BitBucket. Pour ajouter un 
        paquet hébergé sur GitHub, entrez l'URL dans le formulaire 
        https://github.com/username/repo. N'incluez pas .git à la fin ! Les 
        dépôts BitBucket doivent utiliser le format https://bitbucket.org/
        username/repository.
    * _Remove Package_ :
        Pour supprimer le dossier où sont répertoriés les paquets.


Les autres commandes:
---------------------

    * _Add Channel_ (Ajouter un canal):
        Ajoute un autre canal qui répertorie les dépôts. C'est peu courant, 
        mais permet aux utilisateurs de créer un canal personnalisé de dépôts 
        à partager.
    * _Create Package File (Créer un fichier de paquets):
        Fonctionnalité conçue pour les développeurs de paquets, elle prend un répertoire de paquets et génère un fichier _.sublime-package_ qui peut être téléchargé sur le web et référencé dans le fichier _packages.json_ comme dépôt.
    * _Create Binary Package File_ (Créer un fichier binaire de paquet):
        Fonctionnalité conçue pour les développeurs de paquets, elle crée un 
        fichier _.sublime-package_ qui n'inclut pas les fichiers sources 
        _.py_, mais plutôt les fichiers de bytecode _.pyc_. Ceci est utile 
        pour distribuer des paquets commerciaux. Assurez-vous de vérifier le 
        fichier _.sublime-package_ résultant pour vous assurer qu'au moins un 
        fichier _.py_ est inclus afin que Sublime Text puisse charger le 
        paquet. - Fonctionnalité non présente.
    * _Disable Package (Désactive un paquet)
    * _Discover Packages_ (Découvrir les paquets):
        Ouvre un navigateur web à la page 
        <https://packagecontrol.io/#discover> pour découvrir les paquets 
        installables.
    * _Enable Package_ (Activer un paquet):
        Réactive un paquet qui a été désactivé.
    * _Upgrade/Overwrite All Packages (Mise à niveau/Réécriture de tous les 
      paquets):
        Cela permettra de mettre à niveau TOUS les paquets, y compris ceux qui 
        n'ont pas été installés via le contrôle des paquets. Si vous 
        développez une copie personnalisée d'un paquet, vous ne voudrez 
        peut-être pas utiliser cette commande.
    * _Upgrade Package_ (Mettre à jour un paquet):
        Afficher une liste de paquets disponibles pour la mise à jour et 
        laisser l'utilisateur choisir ceux qu'il souhaite mettre à jour.
    * _Install Local Dependecy_ (Installer une dépendance locale)
    * _Package Control Settings – Default_ (Paramètres de contrôle des paquets 
      - Par défaut):
        Ouvre le fichier des paramètres par défaut, qui peut être utilisé 
        comme référence pour modifier les paramètres de l'utilisateur. Toute 
        modification apportée à ce fichier sera perdue lorsque le _Package 
        Control_ sera mis à niveau.
    * _Package Control Settings – User_ (Paramètres de contrôle des paquets - 
      Utilisateur):
        Ouvre les paramètres de l'utilisateur. Toute modification des 
        paramètres doit être enregistrée ici afin qu'elle ne soit pas écrasée 
        lors de la sortie d'une nouvelle version de Package Control.


Synchronisation
===============

Afin de synchroniser correctement vos paquets installés sur différentes 
machines, vous ne voudrez en fait pas synchroniser l'ensemble des répertoires 
_Packages/_ et _Installed Packages/_. La raison en est que certains paquets 
ont des versions différentes pour différents systèmes d'exploitation. En
synchronisant le contenu des paquets entre les systèmes d'exploitation, vous 
risquez de tomber sur des paquets cassés.

La solution est alors d'installer _Package Control_ sur toutes les machines et 
de ne synchroniser que le répertoire _Packages/User/_. Ce répertoire contient 
le fichier _Package Control.sublime-settings_, qui comprend une liste de tous 
les paquets installés. Si ce fichier est copié sur une autre machine, la 
prochaine fois que Sublime Text sera lancé, _Package Control_ installera la 
version correcte de tous les paquets manquants.

Diverses solutions s'offrent à vous, en utilisant _Git_ ou _DropBox_ (cf. 
<https://packagecontrol.io/docs/syncing> - En anglais).


Personnalisation des paquets
============================

Il arrive souvent qu'un paquet fonctionne presque exactement comme vous le
souhaitez, mais quelques petites modifications vont cependant l'améliorer.
Selon la version de Sublime Text que vous utilisez et la façon dont le paquet est installé, vous disposez de quelques options différentes pour personnaliser
un paquet.


Emballage versus déballage
--------------------------

SublimeText3 offre davantage d'options pour cela. Par défaut, les paquets 
seront installés en plaçant le fichier _.sublime-package_ dans le répertoire 
_Install Packages/_. Les utilisateurs peuvent ensuite remplacer les fichiers 
du paquet individuellement en créant un répertoire _Packages/{Package Name}/_ 
et en y plaçant les fichiers édités.

Malheureusement, tous les paquets ne fonctionnent pas lorsqu'ils sont stockés 
dans le fichier _.sublime-package_. Cela est généralement dû au fait que le 
paquet comprend des fichiers tels que des bibliothèques ou des exécutables 
partagés. Si un développeur place un fichier nommé _.no-sublime-package_ dans 
la racine de son paquet, _Control Package_ extraira le paquet dans 
_Packages/{Package Name}/_.

Les paquets stockés dans les fichiers _.sublime-package_ sont nommés "packed", 
tandis que les paquets extraits dans le répertoire _Packages/_ sont nommés 
"unpacked". 


Édition de fichiers déballés
----------------------------

La modification des fichiers d'un paquet déballé n'est pas une bonne idée, 
sauf si vous avez cloné le paquet via _Git/Hg_. En effet, par défaut, 
_Control Package_ met automatiquement à jour les paquets vers la dernière 
version. Cela entraînera l'écrasement de toutes les modifications apportées 
aux fichiers. Si vous rencontrez ce problème, vous pouvez consulter la section 
"Sauvegardes" (infra) pour savoir comment récupérer votre version 
personnalisée d'un fichier.  


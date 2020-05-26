Goto Anything
=============

Permet le changement de fichier tout en étant rapidement positionné sur le 
nouveau fichier. 

Avec un projet ou d'autres fichiers ouverts:
    [Ctrl + P]: liste tous les fichies ouverts, et n'y a plus qu'à 
                sélectionner le fichier voulu (la saisie de quelques lettres
                permet de le positionner en haut de la liste).
    [Ctrl + P] + @ (ou Ctrl + R): Annalyse les fichiers afin de se rendre sur
                                  celui qui contient la chaîne de caractères
                                  saisie.
    [Ctrl + G] + N° de ligne: Le _Goto Line_ permet de se rendre directement à
                              la ligne du fichier ouvert.

Le comportement du _Goto Anything_ peut être défini via les paramètres 
(_settings_).
    - "folder_exclude_patterns" ==> caché dans la barre de navigation du 
      fichier, mais pas dans le _Goto Anything_.
    - "file_exclude_patterns" ==> caché dans la barre de navigation du 
      fichier et dans le _Goto Anything_.
    - "binary_file_patterns" ==> caché dans la barre de navigation du 
      fichier et dans le _Goto Anything_.

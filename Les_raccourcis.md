Les raccourcis
==============

Voir les raccourcis définis: [Preferenes] ==> [key Bindings].
Un fichier s'ouvre à l'image des paramètres (_settings_), il y a un fichier
"default" et un fichier "user".

Exemple:
[
    {
        "keys":["ctrl+u"],
        "command":"nom_commande"
    }
]

Pour connaître le nom d'une commande:
    - [View] ==> [Show console]
    - Dans la console saisir: sublime.log_commands(True) (Pour désativer les 
      logs: sublime.log_commands(False)).
    - Lancer une commande via les menus (Exemple: [Edit] ==> [Copy] lance la 
      commande "Copy", et dans les _logs_ apparait le nom de la commande 
      "Copy").

Définir un nouveau raccourci - La commande [View] ==> [Hide console] (_Montrer 
la console_)
La commande qui apparaît dans les _logs_ est: 
"command = show_panel{"panel":"console","toggle":true}"
Dans le fichier user, saisir:

[
    {
        "keys": ["ctrl+shift+c"],
        "command": "show_panel",
        # Les arguments
        "args":{"panel":"console","toggle":true}
    }
]

Cf. les _key bindings_ sur documentation _non-officielle_.


# rocketchat-archive

Archive des salons publics archivés du chat.fabmob.io. 

## Comment ça marche ? 

Rocketchat permet d'archiver des canaux, mais ils restent présents dans l'interface, perturbant les utilisateurs.

On utilise ici la fonction d'export des messages (trois petits points en haut à gauche du canal), qui nous envoie un zip par email.

Une fois téléchargé, j'utilise les commandes suivantes pour ajouter le canal à l'archive.


```
unzip ARCHIVE_TELECHARGEE -d NOM_DU_SALON && rm ARCHIVE_TELECHARGEE
```
Puis pour renommer le fichier d'export html en index.html qu'il s'affiche directement dans le navigateur : 

```
find . -depth -name '*.html'     -execdir bash -c 'mv -- "$1" "${1//*/index.html}"' bash {} \;

```

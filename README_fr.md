Le post suivant a pour but de montrer un outil open source puissant avec lequel il est vraiment facile de visualiser et de servir les nuages de points depuis notre navigateur.

## Qu'est-ce que Potree ?

D'une manière générale,[Potree](www.potree.org) est un logiciel open source basé sur WebGL, capable de rendre de gros nuages de points.

Dans sa [page web] (www.potree.org) vous pouvez consulter plusieurs exemples de nuages de points obtenus par photogrammétrie ou scanner.

Il est conçu pour fonctionner avec des nuages de points au format LAS, donc si nous voulons transformer un nuage de points, par exemple obtenu par photogrammétrie, nous devrons le transformer auparavant en LAS pour pouvoir transformer le nuage de points au format avec lequel travaille Potree (octrees).

## Téléchargement de logiciels
Pour procéder à l'utilisation de Potree, nous allons télécharger votre logiciel à partir de[www.potree.org/download](http://www.potree.org/download.html).

Sur la page se trouve PotreeConverter, qui est le convertisseur LAS vers octrees et le logiciel lui-même (code source). Cependant, seul PotreeConverter est nécessaire.

## Comment l'exécuter
Avant de commencer, c'est une bonne idée d'installer un serveur web qui fonctionne localement pour que vous puissiez voir le nuage de points (Potree exige certaines permissions sur les navigateurs) sans avoir à le télécharger sur un serveur en tant que tel.

En tant que serveur web, un "simulateur"[Xampp](https://www.apachefriends.org/de/index.html) sera utilisé, qui sera installé dans ``C:\xampp``.

Une fois que vous avez tout décompressé et installé, vous procédez à la transformation du nuage de points. Pour ce faire, ouvrez l'invite de commande (cmd) en écrivant la ligne de code suivante.

```
./PotreeConverter.exe C:/pointcloud.las -o C:/xampp/htdocs/potree --generate-page pageName
```
Où :
- ````./PotreeConverter.exe````` est l'exécutable qui a été téléchargé.
- C:/pointcloud.las``` est le nuage de points que nous voulons transformer.
- ``C:/xampp/htdocs/potree```` est le chemin où il sera sauvegardé.
- ```NomPage````` C'est le nom que nous attribuerons au fichier de sortie

*Il est clair que les chemins peuvent varier selon l'endroit où nous avons placé les fichiers.

Une fois qu'il est exécuté, une fenêtre comme celle-ci devrait apparaître, qui indique que le processus est en cours d'exécution.

![CMD](https://github.com/JoanCano/joancano.io/blob/master/images/imgPotree/resultado.png)

Lorsque le processus est terminé, il est très important que les fichiers générés soient dans ``C:\xampp\htdocs``` pour pouvoir visualiser le nuage de points dans le navigateur :

Vous n'avez donc qu'à ouvrir et visualiser le nuage de points à partir d'un chemin similaire au chemin suivant :

[http://localhost/potree/pageName.html](http://localhost/potree/pageName.html)

## Une petite contribution
Ouvrir la console peut sembler un peu fastidieux, c'est pourquoi le[exécutable] suivant (https://github.com/JoanCano/potreeGUI/blob/master/PotreeConverter.exe) a été créé pour éviter d'avoir à écrire dans la console Windows.

Lors de l'exécution de potreGUI, les fenêtres suivantes apparaissent :
1. il nous demande quel nom nous donnons au dossier
2. Le fichier LAS que nous voulons transformer
3. Le répertoire dans lequel nous voulons le sauvegarder (C:\xampp\htdocs)

![nom](https://github.com/JoanCano/joancano.io/blob/master/images/imgPotree/1.PNG)

&lt;font color=#38B0DE&gt;-=https://github.com/JoanCano/joancano.io/blob/master/images/imgPotree/2.png=- Proudly Presents

&lt;font color=#38B0DE&gt;-=https://github.com/JoanCano/joancano.io/blob/master/images/imgPotree/3.png=- Proudly Presents

## Exemple pratique avec un nuage de points LiDAR du PNOA

Pour montrer le résultat qui peut être obtenu avec un nuage de points LAS, 6 feuilles LiDAR-PNOA ont été utilisées, qui à leur tour ont été jointes dans CloudCompare.

Voici le résultat. Bonne chance !

CMD](https://github.com/JoanCano/joancano.io/blob/master/images/imgPotree/resultado2.PNG)

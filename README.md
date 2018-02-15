Introduction aux humanités numériques
=====================================
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/80x15.png" /></a>

Contenu du cours de L2 « Introduction aux humanités numériques » de [la mineure « Humanités Numériques »](http://www.univ-paris3.fr/mineure-humanites-numeriques-l2--451316.kjsp?RH=1178827308773) de [l'Université Paris 3 Sorbonne Nouvelle](http://www.univ-paris3.fr/).

Ce dépôt contient les données utilisées et les sources du site du cours (diaporama compris).

 - **Site du cours** <https://loicgrobol.github.io/humnum/>
 - **Page du cours sur iCampus** <http://icampus.univ-paris3.fr/course/view.php?id=9961>

## Lancer le diaporama en local
RemarkJS étant prévu pour fonctionner en mode serveur, ouvrir directement [le diaporama](slide/slide.html) risque de ne pas fonctionner hors-connexion.
Pour utiliser le diaporama hors-connextion depuis une archive locale, lancer

```bash
python3 -m http.server
```

dans le dossier racine, puis se rendre à <http://localhost:8000/slide/slide.html>.

## Licence
Copyright © 2017 Loïc Grobol \<loic.grobol@gmail.com\>

Sauf indication contraire, les fichiers présents dans ce dépôt sont distribués selon les termes de la licence [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/).

Un résumé simplifié de cette licence est disponible à <https://creativecommons.org/licenses/by/4.0/>.

Le texte intégral de cette licence est disponible à <https://creativecommons.org/licenses/by/4.0/legalcode>

### Exceptions à la licence

  - [`examples/plotly-latest.min.js`](examples/plotly-latest.min.js) est une copie locale de [Plotly](https://plot.ly/javascript), permettant l'usage hors-ligne de Plotly. Elle est distribuée comme l'original selon les termes de la [licence MIT](https://github.com/plotly/plotly.js/blob/master/LICENSE).
  - [`slide/remark-latest.min.js`](slide/remark-latest.min.js) est une copie locale de [RemarkJS](https://remarkjs.com), permettant l'usage hors-ligne de RemarkJS. Elle est distribuée comme l'original selon les termes de la [licence MIT](https://github.com/gnab/remark/blob/develop/LICENSE).

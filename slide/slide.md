layout: true
name: stat

.bottom-line[Introduction aux Humanités Numériques]

---
class: center, middle, inverse

# Introduction aux Humanités Numériques

### Deuxième partie : (Re)présenter les données

---

template: state

# Détails techniques

### Qui, quand, où
  - Loïc Grobol [`<loic.grobol@gmail.com>`](mailto:loic.grobol@gmail.com)
  - Les mardis de 14h à 16h, salle Bruneau (ILPGA)
  - 2017-11-07 → 2017-12-12

Sur [iCampus](http://icampus.univ-paris3.fr/course/view.php?id=9961) et à <https://loicgrobol.github.io/humnum>.

---

class: center, middle, inverse

# Objectifs

---

# *Previously…*
  - Chercher des données
    - NGrams Viewer
    - Trends
    - Correlate

# Dans cet épisode
**Traiter et (re)présenter des données**

---

#  Présentation (interactive) de données

  - [After Babylon](http://www.puffpuffproject.com/languages.html)
  - [Flying for Thanksgiving](http://googletrends.github.io/iframe-scaffolder/#/view?urls=Thanksgiving%202015%7Chttps:%252F%252Fgoogledataorg.cartodb.com%252Fu%252Fgoogledata%252Fviz%252Fbf595f4c-7381-11e5-9ec5-42010a14800c%252Fembed_map&active=0&sharing=1&autoplay=0&loop=1&layout=narrative&theme=red&title=A%20day%20in%20the%20life:%20US%20Thanksgiving%20on%20Google%20Flights&description=The%20day%20before%20Thanksgiving%202015%20shown%20in%20US%20domestic%20and%20international%20air%20travel%20booked%20with%20Google%20Flights)
  - [Music Timeline](https://research.google.com/bigpicture/music/#)
  - [Mémorial des morts aux frontières de l'Europe](http://owni.fr/2011/02/18/app-la-carte-des-morts-aux-frontieres-de-leurope/)
  - [The depth of the problem](http://apps.washingtonpost.com/g/page/world/the-depth-of-the-problem/931/)

Le but est de présenter les données de façon
  - Claire
  - Plaisante
  - Diffusable

---

# Projet
Réaliser une page web présentant le résultat d'une étude de données.

Le résultat devra être autant que possible
  - Pertinent
  - Clair
  - Plaisant

  - On n'attend évidemment pas des résultats de l'ampleur de ceux présentés précédemment
  - Mais rien ne vous en empêche !

---

class: center, middle, inverse

# *Crash course in web dev*

---

# *Crash course in web dev*

On va suivre les tutoriaux proposés par le [Mozilla Developper Network](https://developer.mozilla.org) en utilisant [Mozilla Thimble](https://thimble.mozilla.org/) comme éditeur pour plus de facilité.

  - Aller à https://thimbleprojects.org/lgrobol/354991
  - Cliquer sur « Remix »

Puis suivre dans l'ordre

  - [Les bases du HTML](https://developer.mozilla.org/fr/Apprendre/Commencer_avec_le_web/Les_bases_HTML)
  - [Les bases du CSS](https://developer.mozilla.org/fr/Apprendre/Commencer_avec_le_web/Les_bases_CSS)
  - [Les bases de Javascript](https://developer.mozilla.org/fr/Apprendre/Commencer_avec_le_web/Les_bases_JavaScript)

D'autres resources à essayer

  - [CSS Zen Garden](http://www.csszengarden.com/)
  - [Le validateur du W3C](https://validator.w3.org/)

---

# La textométrie facile

  1. Aller à https://thimbleprojects.org/lgrobol/350013/
  2. Coller un texte (de préférence assez long) dans la boîte de texte
  3. Cliquer sur « Count »
  4. Expliquer ce qui se passe

On va d'abord essayer de reproduire cet résultat, puis de l'améliorer.

---

# Au commencement
Dans tout ce qui suit, la [documentation web MDN](https://developer.mozilla.org) est votre meilleure amie

  1. Ouvrir un éditeur web
    - [Thimble](https://thimble.mozilla.org)
    - [Plunker](https://plnkr.co/)
    - Un éditeur de texte et votre navigateur favori.
      - En ce qui me concerne : [Atom](http://atom.io) et [Firefox](https://www.mozilla.org/firefox/)
  2. Créer une page HMTL minimale `index.html` (avec Thimble et Plunker, c'est déjà fait !)
  3. Ajouter une zone de texte (`<textarea>`) et un bouton (`<button>`)
  4. Appliquer un style qui vous plaît

---

# Interactivité

  1. En modifiant l'attribut `onclick` du bouton, faire en sorte qu'un clic dessus affiche `hello, world` dans la console
  2. Faire en sorte qu'un clic sur le bouton affiche le contenu de la zone de texte dans la console
  3.  Faire en sorte qu'un clic sur le bouton affiche la liste des mots dans la zone de texte dans la console

---

# Séparation des responsabilités
  1. Dans le même dossier que `index.html`, créer un fichier `script.js` avec le contenu suivant

    ```javascript
    function main(){
        console.log('hello, world')
    }
    ```
  - Ajouter à la fin de `index.html`

    ```html
    <script src="script.js"></script>
    ```
  2. Faire en sorte que `main()` soit déclenché par un clic sur le bouton
  3. Transformer la fonction `main()` pour qu'elle affiche la liste des mots de la zone de texte

---

# Améliorations
  - **Un vrai compteur**
    -Faire en sorte que `main()` affiche la fréquence de chaque mot du contenu de la zone de texte
  - **Un bel affichage**
    - Faire en sorte que les mots, avec leurs fréquences, soient affichés dans un tableau
    - Faire en sorte d'afficher les mots par ordre décroissant de fréquences
  - **De meilleures données**
    - La segmentation (la séparation du texte en mots) n'est pas idéale, l'améliorer
  - D'autres idées ?

---

class: center, middle, inverse

# Extraire et représenter des données

---

# Utiliser Plotly
Dans cette partie on utilisera [https://plot.ly/javascript/](plotly.js)

  1. Aller à <https://thimbleprojects.org/lgrobol/361311> et cliquer sur « Remix »
  2. Examiner le code
    1. Que signifie la ligne 15 ?

       ```htm
       <script src="plotly-latest.min.js" type="text/javascript">
       ```

    2.Ligne 31, Remplacer `'myDiv'` par `'chart'`
      1. Que se passe-t-il ?
      2. Pourquoi ?
      3. Modifier une autre ligne du fichier pour faire réapparaître le graphique

  3. Modifier le code pour que la ligne de « trace0 » soit systématiquement au dessus de celle de « trace1 »
  4. À l'aide de [la documentation de Plotly](https://plot.ly/javascript/line-charts/), modifier le code pour donner un titre au graphique.

---

# Des données plus intéressantes
On s'intéresse ici à la comparaison des espérances de vie des hommes et des femmes en France depuis 1800. Ces données sont issues de <http://www.lifetable.de/>.

  1. Récupérer les données à <https://raw.githubusercontent.com/LoicGrobol/humnum/gh-pages/data/life_expectancy/male-vs-female.tsv>
  2. À l'aide de Plotly, représenter ces données sous forme d'un graphique interprétable, titré et légendé
  3. Modifier à volonté le style de la page et ajouter des attributions pour les données et pour Plotly
  4. Ajouter une courte interprétation du graphique

Exemple à <https://thimbleprojects.org/lgrobol/361199/>

---

# Extraire et formater
On s'intéresse ici à l'alphabétisation, avec pour interrogation :

> Y a-t-il une corrélation simple entre financement de l'éducation et taux d'alphabétisation ?

  1. À partir du site de l'UNESCO <http://data.uis.unesco.org>, récupérer les tables
    - Du taux d'alphabétisation par pays
    - De la part du PIB allouée au budget de l'éducation par pays
  2. Combiner ces tables dans LibreOffice pour obtenir un tableau donnant pour chaque pays la moyenne de chacun de ces indicateurs entre 1999 et 2016
  3. Représenter ces données dans LibreOffice sous forme d'un nuage de points
  4. Proposer une interprétation de ces données et d'éventuelles recherches complémentaires
  5. Exporter ces données au format CSV

---

# À vous de jouer !
À vous de jouer !

Explorer les sources de données suivantes à la recherche d'études intéressantes et réaliser une étude à l'aide de Plotly

  - <http://data.worldbank.org>
  - <http://ourworldindata.org>
  - <http://apps.who.intl/data>
  - <http://data.uis.unesco.org>
  - [CIA World Factbook](https://www.cia.gov/library/publications/the-world-factbook/rankorder/rankorderguide.html)
  - …

---

class: center, middle, inverse

# Ressources supplémentaires

---

# Frantext
<http://www.frantext.fr/>

> *Frantext est une base textuelle à dominante littéraire comportant des textes qui s'échelonnent du Moyen Âge au début du XXIe siècle. En septembre 2015, elle en comptait 4746 dont 85 % issus des XVIIe, XVIIIe, XIXe et XXe siècles.* ([Documentation de Frantext](http://cid.ens-lyon.fr/aide/ac_article.asp?fic=frantext_presentation.asp))

Principalement (en ce qui concerne ce cours) rechercher dans des sous-corpus des fréquences

  - D'un mot
  - Des flexions d'un mot
  - D'une liste arbitraire

Plus d'informations [en annexe](../annexe/humnum_frantext.pdf)

---

# Le Trameur
<http://www.tal.univ-paris3.fr/trameur/>

  - Outil de textométrie **très** complet
    - Recherche dans de gros corpus
    - Recherche avancée
    - Statistiques détaillées
  - Alternative plus légère [iTrameur](http://www.tal.univ-paris3.fr/trameur/iTrameur/)
  - Me contacter si besoin

---

# Gromoteur
<http://gromoteur.ilpga.fr/>

  - Aspiration automatique de sites web
  - Permet de créer rapidement de gros corpus, par exemple à utiliser dans Le Trameur
  - À condition de bien le configurer !
  - Quelques outils statistiques de base (via Nexico)

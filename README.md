# Modèle LaTeX non-officiel pour la rédaction de mémoires de l'Université Jean Monnet - Saint-Étienne
En l'absence de modèle *LaTeX* officiel adapté à la rédaction de mémoires de recherche et/ou de rapports de stage, j'ai essayé d'en créer un au mieux de mes compétences actuelles. La plupart des modifications et redéfinitions de commandes/macros prennent appui sur les recommandations des Presses Universitaires de Saint-Étienne, accessibles ici pour les étudiant∙es : [Consignes PUSE](https://mood.univ-st-etienne.fr/pluginfile.php/739972/mod_resource/content/1/Consignes%20PUSE.pdf).

Toutes corrections ou ajouts extérieurs sont bienvenus afin d'affiner ce modèle au fil du temps.  

Un exemple du résultat final est visible sur le fichier [main.pdf](/main.pdf), à télécharger et ouvrir séparément de préférence car le lecteur intégré de GitHub n'est pas très adapté à sa visualisation.

Dans le cas où vous souhaitez simplement utiliser ce modèle pour l'intégrer à un document *LaTeX* déjà existant, il vous suffit de copier le contenu du fichier [main.tex](/main.tex) jusqu'à la ligne 260 et de le coller dans votre préambule. Pensez toutefois à ensuite éditer les [métadonnées PDF](#métadonnées) qui ne sont pas générées automatiquement.

## Structure
La structure des fichiers peut se séparer en deux parties :
 - D'un côté, le fichier ``main.tex`` contient toutes les modifications nécessaires au respect des normes typographiques ainsi que de la mise en page requise. Le fichier ``biblio.bib`` contient quant à lui un exemple de bibliographie au format *BibLaTeX*.
 - De l'autre, les fichiers commençant par un préfixe numérique (``00_couverture.tex``, ``01_remerciements.tex`` et ``02_introduction.tex``) correspondent aux différentes sous-parties du document. L'idée est de créer autant de sous-fichiers que nécessaire pour chaque chapitre, puis de les ajouter dans le fichier ``main.tex`` à la suite des autres à partir de la ligne 260.

**Note** : La table des matières, bibliographie, et liste des tableaux et/ou figures sont générées automatiquement et ne nécessitent pas de créer de fichiers dédiés.

## Outils recommandés
- [MiKTeX](https://miktex.org/howto/install-miktex) : distribution LaTeX à installer pour pouvoir compiler des documents
- [Zotero](https://www.zotero.org) : nécessaire pour la gestion de la bibliographie
- [Better BibTeX](https://github.com/retorquere/zotero-better-bibtex/releases) : extension pour faire le lien entre Zotero et LaTeX

## Pour travailler avec l'éditeur de code Visual Studio Code (facultatif)
- [Perl](https://strawberryperl.com/) : nécessaire pour compiler les documents
- [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) : extension qui permet de travailler en temps réel
- [Zotero LaTeX](https://marketplace.visualstudio.com/items?itemName=bnavetta.zoterolatex) : extension qui permet de compléter automatiquement ses références bibliographiques depuis Zotero

## Notes
Ce modèle a été pensé pour une compilation avec l'outil standard ``pdflatex``, ou ``latexmk``. XeLaTeX ou LuaLaTeX ne sont pas directement supportés, sauf à adapter certains paquets liés à l'encodage du texte.

### Métadonnées
**Attention** : Les métadonnées PDF sont pour le moment présentes dans le préambule du fichier ``main.tex``, lignes 54-59 :
```
% Inclusion d'hyperliens et des métadonnées PDF :
\usepackage[unicode,
pdfauthor={Prénom NOM},
pdftitle={Titre du mémoire},
pdfsubject={Sujet du mémoire},
pdfkeywords={mots-clés}]{hyperref}
```

Il convient de les modifier de façon adéquate, de même que sur la page de garde qui n'utilise pas les fonctions natives de LaTeX.

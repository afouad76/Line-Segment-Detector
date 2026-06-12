# Détection de Segments de Droite (LSD) en Python

## Présentation

Ce projet consiste en une implémentation pédagogique des principales étapes de l'algorithme **Line Segment Detector (LSD)**, un algorithme de traitement d'image permettant de détecter automatiquement des segments de droite à partir d'une image.

L'objectif est de comprendre les fondements mathématiques et algorithmiques de la détection de lignes en reconstruisant progressivement les différentes étapes de l'algorithme.

Ce travail a été réalisé dans un cadre académique autour du traitement d'image et de l'analyse de gradients.

---

## Objectifs du projet

* Comprendre le fonctionnement interne de l'algorithme LSD.
* Implémenter les principales étapes de détection à partir des gradients d'une image.
* Visualiser les résultats intermédiaires du traitement.
* Manipuler des outils de vision par ordinateur en Python.
* Approfondir les notions de filtrage, gradients et croissance de régions.

---

## Méthodologie

### 1. Redimensionnement et lissage

L'image est d'abord lissée à l'aide d'un filtre gaussien puis redimensionnée afin de réduire les effets d'aliasing et le bruit.

### 2. Calcul des gradients

Les gradients horizontaux et verticaux sont calculés à l'aide des opérateurs de Sobel.

Pour chaque pixel, on détermine :

* le gradient horizontal ;
* le gradient vertical ;
* la norme du gradient ;
* l'orientation du gradient.

### 3. Tri des pixels

Les pixels sont classés selon l'intensité de leur gradient.

Les pixels présentant les gradients les plus élevés sont traités en priorité car ils sont plus susceptibles d'appartenir à des structures significatives.

### 4. Seuillage

Un seuil est appliqué sur la norme du gradient afin d'éliminer les pixels associés au bruit ou à des variations d'intensité peu pertinentes.

### 5. Croissance de région

À partir des pixels les plus significatifs, une procédure de croissance de région regroupe les pixels voisins possédant des orientations compatibles.

Ces ensembles de pixels constituent les **régions de support de ligne**.

### 6. Approximation géométrique

Les régions détectées sont ensuite approximées par des rectangles représentant les segments de droite sous-jacents.

---

## Technologies utilisées

* Python
* NumPy
* OpenCV
* SciPy
* Matplotlib
* Jupyter Notebook

---

## Images de test

Le développement initial a été réalisé sur des images synthétiques simples :

* carré plein ;
* contour carré.

Ces exemples permettent de vérifier visuellement chaque étape de l'algorithme avant de passer à des images réelles plus complexes.

---

## Résultats obtenus

L'algorithme permet de :

* calculer les cartes de gradients ;
* identifier les zones présentant de fortes variations d'intensité ;
* construire des régions de support cohérentes ;
* obtenir une approximation géométrique des structures linéaires présentes dans l'image.

Des visualisations intermédiaires sont fournies dans le notebook afin d'illustrer le comportement de chaque étape.

---

## Perspectives d'amélioration

Plusieurs extensions sont envisagées :

* implémentation complète de l'algorithme LSD original ;
* tests sur des images réelles (bâtiments, routes, documents, panneaux) ;
* amélioration de la robustesse au bruit ;
* optimisation des performances ;
* comparaison avec d'autres méthodes de détection de contours et de lignes (Canny, Transformée de Hough).

---

## Structure du dépôt

```text
.
├── rapport_lsd.ipynb
├── carre.jpg
├── carrenoir.jpg
└── README.md
```

---

## Compétences mobilisées

* Traitement d'image
* Vision par ordinateur
* Analyse de gradients
* Algorithmes de détection de contours
* Géométrie numérique
* Python scientifique
* Visualisation de données

---

## Auteur

**Fouad Almahaboub**

Master MMAS – Mathématiques, Modélisation et Apprentissage Statistique

Université Paris Cité

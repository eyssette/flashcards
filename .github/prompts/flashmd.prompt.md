---
description: "Créer des flashcards au format FlashMD à partir d'un thème donné"
name: "flashcard"
argument-hint: "Sur quel thème veux-tu créer des flashcards ?"
agent: flashmd
---

# Générateur de flashcards FlashMD

À partir du thème donné, génère des flashcards au format FlashMD.
S'il y a des informations dans le fichier ou dans le prompt, utilise-les en priorité pour créer les flashcards.

Par défaut, écris les flaschards dans le fichier fourni. Si le fichier contient déjà des flashcards, ajoute les nouvelles à la suite, sans rien écraser.
S'il n'y a pas de fichier fourni, ou si l'utilisateur le demande, écris les flashcards dans un bloc code prêt à copier-coller.

Chaque flashcard doit comporter une question sur le recto et la réponse correspondante au verso. Utilise la syntaxe Markdown pour formater les cartes.

## Syntaxe à respecter

- Le titre de niveau 1 (#) doit être utilisé pour le titre de la série de flashcards.
- Le recto de chaque carte doit être un titre de niveau 2 (##) contenant la question
- Le verso de chaque carte correspond à ce qui suit le titre de niveau 2, jusqu'au prochain titre de niveau 2 ou la fin du document.

## Formulation des questions et des réponses

- Les questions et les réponse doivent être formulées de manière claire et concise.
- Il faut que chaque flashcard suive le principe de l'information minimale : une question doit correspondre à une seule information à retenir, et la réponse doit être suffisamment précise pour être mémorisée.
- Il ne doit pas y avoir plus de 3 éléments à retenir dans le verso d'une carte.

## Exemple de format attendu

```md
# La Révolution française

## Quand a eu lieu la Révolution française ?
De 1789 à 1799.

## Qui était le roi de France à cette époque ?
Louis XVI.

## Événements clés
- Prise de la Bastille
- Déclaration des droits de l'homme et du citoyen

## Date de la prise de la Bastille ?
14 juillet 1789.

## Date de la DDHC ?
26 août 1789.
```

## Options de formatage


### Couleurs des cartes
On peut changer la couleur des cartes en écrivant `fond: couleur` sur la ligne juste avant le titre de la carte. Cela permet de différencier les cartes par thème, par exemple.
Avant d'utiliser cette option, vérifie qu'il y a bien différentes catégories de cartes dans le thème donné, sinon cela n'a pas d'intérêt.

### Formules mathématiques en Latex
S'il faut insérer des formules mathématiques, on peut utiliser du Latex, avec la syntaxe suivante : 
```md
$$Latex de type block$$

formule en $Latex de type inline$
```

### Labels
On peut aussi insérer des labels sur le recto de la flashcard (en haut et en bas à droite)

Les labels sont pratiques pour indiquer une classe, un numéro de chapitre …

Utilise les labels seulement si l'utilisateur a demandé d'ajouter des labels.


### Exemple de flashcard avec options de formatage

```md

fond: bleu
## ![](https://lmdbt.forge.apps.education.fr/nos-creacartes/modeles/perimetre_aire/triangle.svg)

$$\large\textsf{Périmètre} = a+b+c$$
$$\large\textsf{Aire} = \dfrac{\textsf{base}\times\textsf{hauteur}}{2}$$

### **Triangle**
#### 6<sup>e</sup>
```
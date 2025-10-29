# Désambiguïsation d’inventeurs dans les bases de brevets

## Objectif du projet
Ce projet avait pour objectif de développer une méthode de **désambiguïsation d’inventeurs** dans les bases de données de brevets.  
Le but était d’identifier correctement les inventeurs, même lorsque leurs noms apparaissent sous différentes formes, afin de leur attribuer un **identifiant unique**.  
Ce travail a été réalisé dans un cadre académique et s’inscrivait dans une réflexion plus large sur la qualité et la fiabilité des données de brevets.

---

## Contexte
Les bases de données de brevets (telles que celles de l’Office Européen des Brevets) comportent fréquemment des incohérences dans les informations relatives aux inventeurs :  
variations orthographiques, erreurs de saisie, doublons, ou encore affiliations incomplètes.  
Ces imprécisions rendent difficile toute analyse statistique ou économique sur la productivité, la mobilité ou la collaboration des inventeurs.  

Le projet visait donc à proposer une **approche algorithmique de désambiguïsation** s’appuyant sur les métadonnées disponibles (nom, adresse, pays, société, etc.).

---

## Méthodologie

### 1. Préparation et nettoyage des données
- Importation et intégration des données de plusieurs tables (brevets, inventeurs, technologies, etc.)  
- Identification et suppression des lignes non exploitables  
- Normalisation des noms et adresses à l’aide de fonctions de traitement textuel  
- Mise en place d’index pour optimiser les requêtes sur plusieurs millions de lignes  

### 2. Désambiguïsation
- Comparaison des chaînes de caractères (distance de Levenshtein, correspondance floue)  
- Attribution d’un identifiant unique (`psn_id`) à chaque inventeur reconnu  
- Regroupement des enregistrements similaires selon la proximité du nom, de l’affiliation et du pays  
- Prise en compte de la fréquence d’apparition pour éviter les regroupements erronés  

### 3. Outil d’exploration
- Développement d’un script permettant de saisir un nom d’inventeur et de retrouver tous les brevets associés  
- Ajout d’un mécanisme de suggestion automatique en cas d’erreur de saisie  
- Test de l’algorithme sur un sous-échantillon représentatif de la base  

---

## Résultats
Les résultats obtenus ont montré que l’approche permettait de **réduire significativement le nombre de doublons** et d’améliorer la cohérence globale des données.  
Cependant, certaines limites ont été observées, notamment dans les cas d’homonymie (inventeurs partageant un même nom) et pour les inventeurs dont les informations d’adresse étaient incomplètes.  
Ces résultats restent donc **mitigés**, mais constituent une base solide pour une automatisation future plus précise.

---

## Contenu du dépôt

| Fichier | Description |
|----------|-------------|
| `Rapport+Documentation_technique.pdf` | Rapport complet décrivant la structure de la base, la logique de désambiguïsation et les tests réalisés |
| `Presentation_Disambiguation.pdf` | Présentation synthétique du projet et des principales étapes de mise en œuvre |

---

## Perspectives
Plusieurs améliorations ont été envisagées pour la suite :
- Intégration de techniques de machine learning supervisé pour renforcer la détection des doublons  
- Extension de la méthode à d’autres bases de brevets (notamment celles de l’USPTO)  
- Création d’une interface graphique complète pour interagir avec la base et visualiser les liens entre inventeurs  

---


Projet réalisé dans le cadre d’un travail universitaire à **CY Tech**.  


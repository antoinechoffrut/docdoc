---
layout: post
title:  "Disponibilité à La Permanence"
published: true
date:   2019-11-12 10:40:00 +0000
categories: analytics
---

---

**Avertissement.**  
Ce site est une inititative personnelle et ne dépend pas de La Permanence. Les informations sont données sans aucune garantie d'exactitute.

--- 

  
# La Permanence  

[La Permanence](https://www.la-permanence.com) offre à ce jour trois
espaces de travail dans Paris:  
- 2 rue du Fer à Moulin (5ème): 65 places  
- 48 bis rue d'Alésia (14ème): 82 places  
- 52 rue Marcadet (18ème): 55 places  

# Les données  
La récolte des données a débuté vers le début du mois de janvier 2019
à partir de l'affichage sur le site de La Permanence.  L'espace de
travail rue Marcadet a ouvert au mois d'août 2019.

# Tendances sur une semaine et aperçu des 7 derniers jours  

L'illustration ci-dessous affiche, pour l'espace Rue du Fer à Moulin,  
- (en noir) les données des 7 jours précédents la date indiquée
- (en rouge) les tendances historiques: 
  - la zone la plus foncée correspond à 20% des valeurs autour de la  médiane,
  - la zone intermédiaire correpond à 60% des valeurs autour de la  médiane,
  - la zone la  plus claire correspond à 96% des valeurs autour de la médiane.  

À noter qu'un lissage sur 30 minutes a été effectué.  

<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/moulin-weekly-summary.png"
alt="Disponibilité - Rue du Fer à Moulin"/> </p>

De même, les illustrations ci-dessous affichent les valeurs
correspondantes pour les espaces Rue d'Alésia (en bleu) et Rue
Marcadet (en vert).  

<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/alesia-weekly-summary.png"
alt="Disponibilité - Rue d'Alésia"/> </p>


<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/marcadet-weekly-summary.png"
alt="Disponibilité - Rue Marcadet"/> </p>

On constate donc des dynamiques différentes dans les trois espaces de
travail.  



# Moyennes journalières  
Les figures ci-dessous représentent les moyennes journalières pour
chaque espace de travail

<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/moulin-historical-daily-averages.png"
alt="Profils statistiques par jour de la semaine - Rue du Fer à Moulin"/> </p>

<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/alesia-historical-daily-averages.png"
alt="Profils statistiques par jour de la semaine - Rue d'Alésia"/> </p>

<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/marcadet-historical-daily-averages.png"
alt="Profils statistiques par jour de la semaine - Rue Marcadet"/> </p>


Il semble donc que les vacances scolaires n'aient pas d'incidence sur
la disponibilité journalière moyenne dans les divers espaces de
travail.  En revanche, on peut s'attendre à des dynamiques
différenciées dans la journée (*analyse à venir*).

# Tendances par jour de la semaine  
Les diagrammes ci-dessous donnent les profils statistiques des
moyennes journalières par jour de la semaine et pour chaque espace de
travail.  Il s'agit de diagrammes en boîte ou boîtes de Tukey
(*boxplots*):   
- la **barre verte** indique la valeur médiane  
- le **rectangle** indique les 50% des valeurs réparties équitablement de
  part et d'autre de la médiane, c'est à dire les valeurs entre le
  premier quartile (Q1) et le troisième quartiles (Q3);  
- les **segments** ont, en général, pour longueur une fois et demi la
  différence Q3 - Q1; plus précisément,
  - l'extrémité haute du segment supérieur est la plus grande valeur
  dans le jeu de données n'excédant pas Q3 + 1.5 (Q3-Q1)  
  - l'extrémité basse du segment supérieur est la plus petite valeur
  n'allant pas en dessous de Q1 - 1.5(Q3-Q1)  
- les **valeurs aberrantes** sont indiquées par des circles  


<p align="center"> <img src="{{site.baseurl}}/assets/la-permanence/moulin-boxplot-by-day-of-week.png"
alt="Profils statistiques par jour de la semaine - Rue du Fer à
Moulin"/> </p>

<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/alesia-boxplot-by-day-of-week.png"
alt="Profils statistiques par jour de la semaine - Rue d'Alésia"/> </p>

<p align="center"> <img
src="{{site.baseurl}}/assets/la-permanence/marcadet-boxplot-by-day-of-week.png"
alt="Profils statistiques par jour de la semaine - Rue Marcadet"/> </p>

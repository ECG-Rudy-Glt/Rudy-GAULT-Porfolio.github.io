---
title: Projet GSB (Ecole)
publishDate: 2020-03-02 00:00:00
img: /assets/GSB.png
img_alt: Iridescent ripples of a bright blue and pink liquid
description: |
tags:
  - Design
  - Dev
  - User Testing
---
Projet GSB - Gestion des visites
[Retrouvez ici le document complet du projet.](../../public/assets/GSB.pdf)


Github du projet: https://github.com/ECG-Rudy-Glt/Projet-GSB---Gestion-des-visites.git



Description textuelle des cas d’utilisation
Cas : gérer les rapports de visite
Scénario classique
1) Le visiteur demande à créer un nouveau rapport de visite
2) Le système retourne un formulaire avec la liste des médecins et des champs de saisie
3) Le visiteur sélectionne un médecin à partir de son début de nom, sélectionne la date et remplit
les différents champs, sélectionne les médicaments et les quantités offertes et valide
4) Le système enregistre le rapport
Scénario étendu : modification d’un rapport
5) Le visiteur demande à modifier un rapport
6) Le système retourne un formulaire avec une date à sélectionner
7) Le visiteur sélectionne la date
8) Le système retourne les rapports que le visiteur a effectués à cette date
9) Le visiteur sélectionne un rapport de visite
10) Le système retourne les informations déjà saisies concernant le motif et le bilan
11) Le visiteur modifie les informations
12) Le système enregistre les modifications
Scénario alternatif
4.1) Des champs ne sont pas remplis, le système en informe le visiteur, retour à 3
Cas : gérer les médecins
Scénario classique
1) Le visiteur demande à voir les informations concernant un médecin
2) Le système retourne un formulaire avec un champ de recherche du médecin
3) Le visiteur sélectionne un médecin à partir de son début de nom et valide
4) Le système retourne les informations personnelles concernant ce médecin
Scénario étendu :
5) Le visiteur clique sur l’adresse de messagerie du médecin
6) Le système permet la rédaction et l’envoi d’un courriel
7) Le visiteur demande à voir tous les anciens rapports de visite concernant ce médecin
8) Le système retourne tous ses rapports
9) Le visiteur demande à modifier certains champs concernant des informations du médecin
10) Le système enregistre ces modifications
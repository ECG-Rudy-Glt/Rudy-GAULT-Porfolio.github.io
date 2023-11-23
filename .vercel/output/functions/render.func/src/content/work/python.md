---
title: Projets Algorithmie Python (Ecole)
publishDate: 2019-10-02 00:00:00
img: /assets/veille.png
img_alt: Soft pink and baby blue water ripples together in a subtle texture.
description: |

tags:
  - Python
  - Algo
---

<h2>Exemples jeux Python 1e année. </h1>

<H5> Vérificateur de Palindrome en Python </H5>

Ce script verifie si un mot est un palindrome ou non :

```python
def est_palindrome(phrase):
    # On nettoie la phrase en enlevant les espaces, la ponctuation et en mettant en minuscule
    phrase_propre = ''.join(char.lower() for char in phrase if char.isalnum())
    # On compare la chaîne nettoyée à sa version inversée
    return phrase_propre == phrase_propre[::-1]

# Exemple d'utilisation
texte = input("Entrez un texte pour vérifier s'il s'agit d'un palindrome : ")
if est_palindrome(texte):
    print("C'est un palindrome !")
else:
    print("Ce n'est pas un palindrome.")

```

<H5> Générateur de Mot de Passe en Python </H5> 

Ce script génère un mot de passe sécurisé avec une combinaison aléatoire de lettres, chiffres et symboles :

```python
import random
import string

def generer_mot_de_passe(taille):
    caracteres = string.ascii_letters + string.digits + string.punctuation
    mot_de_passe = ''.join(random.choice(caracteres) for i in range(taille))
    return mot_de_passe

taille = int(input("Entrez la taille du mot de passe : "))
print("Votre nouveau mot de passe est : ", generer_mot_de_passe(taille))
```


<H5> Tic-Tac-Toe </H5>

Un jeu de Tic-Tac-Toe simple pour deux joueurs jouant à tour de rôle dans la console.

```python
def afficher_plateau(plateau):
    for ligne in plateau:
        print(" | ".join(ligne))
    print()

def prise_de_position(plateau, position, joueur):
    ligne, colonne = position
    plateau[ligne][colonne] = joueur

def verifier_gagnant(plateau, joueur):
    # Vérifier les lignes
    for ligne in plateau:
        if all(cellule == joueur for cellule in ligne):
            return True
    # Vérifier les colonnes
    for colonne in range(3):
        if all(plateau[ligne][colonne] == joueur for ligne in range(3)):
            return True
    # Vérifier les diagonales
    if all(plateau[i][i] == joueur for i in range(3)) or all(plateau[i][2 - i] == joueur for i in range(3)):
        return True
    return False

def jeu_tic_tac_toe():
    plateau = [[" " for _ in range(3)] for _ in range(3)]
    joueur_actuel = "X"
    while True:
        afficher_plateau(plateau)
        try:
            position = input(f"Joueur {joueur_actuel}, entrez votre coup (ligne,colonne): ")
            ligne, colonne = map(int, position.split(','))
            if plateau[ligne][colonne] != " ":
                print("Position occupée. Essayez à nouveau.")
                continue
        except (ValueError, IndexError):
            print("Entrée invalide. Assurez-vous de saisir ligne,colonne.")
            continue
        prise_de_position(plateau, (ligne, colonne), joueur_actuel)
        if verifier_gagnant(plateau, joueur_actuel):
            afficher_plateau(plateau)
            print(f"Joueur {joueur_actuel} a gagné!")
            break
        if all(cellule != " " for ligne in plateau for cellule in ligne):
            afficher_plateau(plateau)
            print("Match nul!")
            break
        joueur_actuel = "O" if joueur_actuel == "X" else "X"

 jeu_tic_tac_toe()

```



<H5> Jeu du Devine Nombre </H5>

Un jeu où l'ordinateur choisit un nombre aléatoire et le joueur doit le deviner.

```python
import random

def jeu_devine_nombre(max_nombre):
    nombre_secret = random.randint(1, max_nombre)
    nombre_devine = 0

    while nombre_devine != nombre_secret:
        nombre_devine = int(input(f"Devinez le nombre entre 1 et {max_nombre}: "))
        if nombre_devine < nombre_secret:
            print("Plus grand...")
        elif nombre_devine > nombre_secret:
            print("Plus petit...")
    
    print(f"Félicitations! Le nombre était {nombre_secret}.")

jeu_devine_nombre(100)
```
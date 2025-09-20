import time
import sys
import random

bot_name = "DPPS8"
bot_age = 250

print(f"Salut!\n\nJe suis {bot_name}, droïde de protocole, programmé pour servir.\n")
time.sleep(0.5)

player_name = input("Comment tu t'appelles ?\n\n")

print(f"\nTu t'appelles {player_name}? \nJamais entendu...\nC'est original!\n")
time.sleep(0.5)

print(f"Dis-moi {player_name}, tu avais déjà entendu le nom {bot_name} avant d'arriver par ici ?\n")
answer = input("")
time.sleep(0.5)

print(f"\nEt oui, je comprends.\n\nMon scan me dit que tu aurais dans les...\n")
player_age = int(input("Hum... Tu as quel âge en fait ? \n(réponds en chiffres seulement)\n\n"))

if player_age >= 115:
    time.sleep(0.5)
    print("\nC'est impossible! Tu n'es qu'un humain!\n")
elif player_age >= 18:
    time.sleep(0.5)
    print(f"\n{player_age} ans... c'est jeune! \nMoi j'ai {bot_age} ans!!!\n")
else:
    time.sleep(0.5)
    print("\nMais tu n'as rien à faire ici, je te déconnecte.")
    for i in range(9):
        time.sleep(0.3)
        print("offline")
    sys.exit()

time.sleep(0.5)
print("Mais ça n'a pas vraiment d'importance... \n\nAllez suis-moi!\n")
time.sleep(0.5)

door = 0  # Porte fermée
print("Ah!\n")
time.sleep(0.5)
print("La porte est fermée.\n")
time.sleep(0.5)

# Tant que la porte est fermée
while door == 0:
    print("Tu veux que j'ouvre la porte de la cité?\n")
    time.sleep(0.5)

    choice = input("Appuie sur Oui pour ouvrir la porte, Non pour la laisser fermée : ").lower()

    if choice == "oui":
        door = 1
        time.sleep(0.5)
        print("\nTu as ouvert la porte !\n")

    elif choice == "non":
        time.sleep(0.5)
        print("\nSi on ouvre pas la porte on ne va pas pouvoir faire grand chose...\n")

    else:
        time.sleep(0.5)
        print("\n🚨!!! Choix invalide !!!🚨\n")

time.sleep(0.5)
print(f"La porte est ouverte! Nous allons pouvoir visiter la salle des archives, suis-moi!\n\n")
time.sleep(0.5)
print("Hum..\n\n")
time.sleep(0.5)
print("Avant d'y aller ça te tente une partie de Pierre-Feuille-Ciseaux?\n")
time.sleep(0.5)

game = 0
while game == 0:
    choice = input("Appuie sur Oui pour jouer, Non pour refuser : ").lower()
    if choice == "oui":
        game = 1
        time.sleep(0.5)
        print(f"\nParfait, prépare toi à perdre {player_name} !\n")

        # Mini-jeu
        options = ["pierre", "feuille", "ciseaux"]

        print("\nLe premier à gagner 3 manches l'emporte.\n")

        player_score = 0
        bot_score = 0

        while player_score < 3 and bot_score < 3:
            player = input("Pierre? Feuille? Ciseaux? : ").lower()
            if player not in options:
                print("\nHmm... ça n'existe pas dans mes fichiers. Réessaie.\n")
                continue

            bot_choice = random.choice(options)
            print(f"\n{bot_name} joue : {bot_choice}")

            if player == bot_choice:
                print("\nÉgalité !")
            elif (player == "pierre" and bot_choice == "ciseaux") or \
                 (player == "feuille" and bot_choice == "pierre") or \
                 (player == "ciseaux" and bot_choice == "feuille"):
                player_score += 1
                print(f"\nBien joué {player_name}, tu gagnes cette manche..")
            else:
                bot_score += 1
                print("\nHa ha ! Manche pour moi!")

            print(f"Score : {player_name} {player_score} – {bot_name} {bot_score}")
            time.sleep(0.5)

        # Fin du mini-jeu
        if player_score == 3:
            print(f"\nBravo {player_name}, tu as gagné la partie... curieux. Pour un humain.\n")
        else:
            print("\nAh ah, j’ai gagné misérable humain! Mais pas de panique, je suis un robot après tout.\n")

        time.sleep(0.5)
        print("Bon... reprenons notre chemin vers la salle des archives\n")

    elif choice == "non":
        game = 2
        time.sleep(0.5)
        print("Bon... reprenons notre chemin vers la salle des archives\n")

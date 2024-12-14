#!/bin/bash

# Function to get the number of files in the current directory
function count_files {
    ls -1 | wc -l
}

echo "Bienvenue dans le jeu de devinettes !"
correct_count=$(count_files)

while true; do
    echo "Combien de fichiers se trouvent dans le répertoire actuel ?"
    read user_guess

    if [[ $user_guess -eq $correct_count ]]; then
        echo "Félicitations ! Vous avez deviné correctement."
        break
    elif [[ $user_guess -lt $correct_count ]]; then
        echo "Trop bas ! Essayez encore."
    else
        echo "Trop haut ! Essayez encore."
    fi
done

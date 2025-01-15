Les grandes étapes de *mes* solutions aux exercices.

# Etapes
## fprime
1. Vérifier si nbr est égal à 1. Si oui, imprimer 1.
2. Réutiliser la structure de **is_prime(nbr)**, avec quelques nuances:
   - une variable qui stocke le facteur assignée à 2, car tous les chiffres sont divisibles par 1 et aucun par zéro, on commence donc par le premier chiffre qui a un intérêt. (identique à is_prime)
   - une variable qui indique si on est sur le premier facteur ou un suivant, ce qui permet de savoir quand écrire l'étoile de la multiplication. (différent de is_prime)
   - tant que le facteur est plus petit (identique à is_prime) ou égal (différent de is_prime) que nbr: vérifier si le modulo de nbr par le facteur est égal à 0 (identique à is_prime) ET si le facteur est un nombre premier via is_prime (différent de is_prime).
     si true: vérifier si on est sur le premier facteur pour savoir si on doit print l'étoile ou pas; print le facteur, puis diviser nbr par le facteur. (différent de is_prime)
     si false: incrémenter le facteur. (identique à is_prime)
     
## itoa
1. Compter le nombre d'éléments (chiffres + signe potentiel) avec **get_nelem(nbr)**.
2. Allouer de la mémoire à la string avec **malloc()**, de la taille du nombre d'éléments + 1. Vérifier si l'allocation a fonctionné.
3. Copier nbr dans une temporaire.
4. Vérifier si nbr est négatif et s'il est spécifiquement égal à int_min, prendre les dispositions nécessaires. Si négatif, assigner '-' au premier char de ma string et 1 à la variable qui servira de condition de sortie au while. Sinon, assigner 0 à cette variable.
5. Copier nelem dans une temporaire.
6. Tant que cette copie de nelem est plus grande que la variable mise à 0 ou à 1: la décrémenter puis assigner la copie de nbr % 10 (en char!) au char indexé par la copie de nelem. Diviser la copie de nbr par 10.
7. Vérifier si nbr est spécifiquement égal à int_min: si oui, assigner 8 (en char!) au dernier char de la string.
8. Fermer la string.
9. Retourner la string.

## split
1. Compter le nombre de mots avec **word_count(str)**:
  - Tant que la string n'a pas été entièrement parcourue,
  - vérifier si : 
      on est au premier char ET le char actuel n'est pas un espace avec **is_in_set(c)**
      
      OU

      le char précédent est un espace ET le char actuel n'est pas un espace

      si true, incrémenter le nombre de mots.
  - incrémenter l'index.
2. Allouer de la mémoire au tableau avec **malloc()**, de la taille du nombre de mots + 1. Vérifier si l'allocation a fonctionné.
3. Remplir le tableau:
  - tant que la string n'a pas été entièrement parcourue ET que l'index des mots est plus petit que le nombre de mots,
  - vérifier si le char actuel n'est pas un espace.
    si true, appeler la fonction **fill(string + index des chars)**, qui définit la fin du mot actuel, puis qui alloue de la mémoire de la taille de ce mot (avec **w_len(str)** et le remplit des char via **ft_substr(str, start, len)**.
  - vérifier si l'allocation a fonctionné. PAS DE FREE() EN EXAMEN : sur cet exercice, les leaks ne sont pas verifiés et **free()** n'est d'ailleurs pas autorisé.
  - incrémenter l'index des chars avec la longueur du mot via **ft_strlen(str)**.
  - incrémenter l'index des mots.
  - finir le tableau avec un NULL.
4. Retourner le tableau.

## rev_wstr
1. Compter la longueur de la string avec **ft_strlen(str)**.
2. Tant que la longueur est plus grande ou égale à zéro:
   - Tant que le char actuel est '\0', un espace ou une tabulation: décrémenter la longueur. On cherche la dernière lettre du dernier mot, et on en stocke l'index dans une variable.
   - Tant que le char actuel n'est pas '\0', un espace ou une tabulation: décrémenter la longueur. On cherche la première lettre du dernier mot, et on en stocke l'index dans une variable.
   - Copier l'index de la première lettre du dernier mot dans une temporaire. Elle permettra de savoir quand écrire ou non un espace (avant chaque mot, sauf pour le premier).
   - Tant que l'index de la première lettre du dernier mot est plus petit ou égal à l'index de la dernière lettre du dernier mot: imprimer le char indexé (première lettre), incrémenter l'index.
   - Vérifier si on est pas sur le premier mot: si true, imprimer un espace.

## rostring

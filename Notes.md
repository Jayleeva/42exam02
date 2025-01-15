# split
## Etapes
1. Compter le nombre de mots avec **word_count(str)**:
  - Tant que la string n'a pas été entièrement parcourue,
  - vérifier si : 
      on est au premier char ET le char actuel n'est pas un espace avec **is_in_set(c)**
      
      OU

      le char précédent est un espace ET le char actuel n'est pas un espace

      si true, incrémenter le nombre de mots.
  - incrémenter l'index.
2. Allouer de la mémoire au tableau avec **malloc()**, de la taille du nombre de mots. Vérifier si l'allocation a fonctionné.
3. Remplir le tableau:
  - tant que la string n'a pas été entièrement parcourue ET que l'index des mots est plus petit que le nombre de mots,
  - vérifier si le char actuel n'est pas un espace.
    si true, appeler la fonction **fill(string + index des chars)**, qui définit la fin du mot actuel, puis qui alloue de la mémoire de la taille de ce mot (avec **w_len(str)** et le remplit des char via **ft_substr(str, start, len)**.
  - vérifier si l'allocation a fonctionné. PAS DE FREE() EN EXAMEN : sur cet exercice, les leaks ne sont pas verifiés et **free()** n'est d'ailleurs pas autorisé.
  - incrémenter l'index des chars avec la longueur du mot via **ft_strlen(str)**.
  - incrémenter l'index des mots.
  - finir le tableau avec un NULL.
4. Retourner le tableau.

# itoa
## Etapes

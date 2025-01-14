# split
## Etapes
1. Compter le nombre de mots:
  - Tant que la string n'a pas ete entierement parcourue,
  - verifier si : 
      on est au premier char ET le char actuel n'est pas un espace
      
      OU

      le char precedent etait un espace ET le char actuel n'est pas un espace

      si true, incrementer le nombre de mots.
  - incremeter l'index.
2. Allouer de la memoire au tableau avec **malloc()**, de la taille du nombre de mots. Verifier si l'allocation a fonctionne.
3. Remplir le tableau:
  - tant que la string n'a pas ete entierement parcourue ET que l'index des mots est plus petit que le nombre de mots,
  - verifier si le char actuel n'est pas un espace.
    si true, appeler la fonction **fill(string + index des chars)**, qui definit la fin du mot actuel, puis qui alloue de la memoire de la taille de ce mot et le remplit des char via **ft_substr(str, start, len)**.
  - verifier si l'allocation a fonctionne. EN EXAMEN: PAS DE FREE(), les leaks ne sont pas verifies sur cet exercice et free() n'est pas autorise.
  - incrementer l'index des chars de la longueur du mot via **ft_strlen(str)**.
  - incrementer l'index des mots.
  - finir le tableau avec un NULL.
4. Retourner le tableau.

# Algorithme de recherche binaire
def recherche_binaire(liste, element):
    """
    Effectue une recherche binaire dans une liste triée.
    Args:
        liste (list): La liste triée dans laquelle effectuer la recherche.
        element: L'élément à rechercher.
    Returns:
        int: L'indice de l'élément dans la liste, ou -1 s'il n'est pas présent.
    """
    debut, fin = 0, len(liste) - 1
    while debut <= fin:
        milieu = (debut + fin) // 2
        if liste[milieu] == element:
            return milieu
        elif liste[milieu] < element:
            debut = milieu + 1
        else:
            fin = milieu - 1
    return -1

# Exemple d'utilisation
if __name__ == "__main__":
    ma_liste = [2, 5, 8, 12, 16, 23, 38, 45, 56]
    element_recherche = 23
    resultat = recherche_binaire(ma_liste, element_recherche)
    if resultat != -1:
        print(f"L'élément {element_recherche} se trouve à l'indice {resultat}.")
    else:
        print(f"L'élément {element_recherche} n'est pas présent dans la liste.")

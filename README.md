
# Partie théorique : XPATH (environ 20 minutes)

#### 1 Retourner tous les éléments book

/library/book

#### 2 Retourner tous les éléments title ayant comme parent un élément book avec un attribut type égal à roman

/library/book[type=roman]/title

#### 3 Retourner le nombre d'éléments book ayant un attribut type égal à bd

/library/book[type=bd]/title

#### 4 Que renvoie la requête XPath suivante :  /library/library/ancestor-or-self::library

Sélectionne tous les ancêtres de bibliothèque du nœud actuel - et le courant également s'il s'agit d'un nœud de bibliothèque


# Partie 2 : Application web (environ 1h10 minutes)

sauvegarde une nouvelle Personne.

```
public function postCreate()
{
    // nouvelle instance de l'attribut
    $newPersonne = new Personne();
    // setter pour personne
    $newPersonne->setLastname($lastname);
    // on crée l'entity manager
    $em = $this->getDoctrine()->getManager();
    // on persiste les données du nouvel article
    $em->persist($newPersonne);
    // on flush
    $em->flush();
    // on retourne un json pour ne pas avoir un bug à l'affichage de la page
    return $this->json('Personne créée');
}
```
renvoie toutes les Personnes enregistrées par ordre alphabétique

```
SELECT * FROM Personne 
ORDER BY lastname
```

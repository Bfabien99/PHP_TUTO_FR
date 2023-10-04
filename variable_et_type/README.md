# VARIABLE ET TYPES
En PHP, les variables et les types de données sont des concepts fondamentaux. Les variables sont utilisées pour stocker des données, tandis que les types de données déterminent le type de données que vous pouvez stocker dans une variable. Voici une explication des variables et des types de données en PHP :

## Déclaration de variables
En PHP, vous pouvez déclarer une variable en utilisant `le signe dollar ($) suivi du nom de la variable`. Les noms de variables sont `sensibles à la casse`, ce qui signifie que `$nom` et `$Nom` sont `deux variables différentes`.

## Attribution de valeurs aux variables
Pour attribuer une valeur à une variable, utilisez l'opérateur d'attribution `=`.
```php
<?php
$nom = "John";
$age = 25;
?>
```

## Types de données en PHP
PHP prend en charge plusieurs types de données. Les principaux types de données en PHP sont les suivants :
- `Entier (integer)` : Représente des nombres entiers.
```php
<?php
$age = 25;
?>
```

- `Nombre à virgule flottante (double)` : Représente des nombres décimaux.
En programmation, la virgule(,) est représentée par un `point(.)`
```php
<?php
$moyenne = 12.50;//12,50
?>
```


- `Chaîne de caractères (string)` : Représente du texte.
Les chaînes peuvent être placées entre guillemets simples `''` ou doubles `""`
```php
<?php
$git = "Bfabien99";
?>
```

- `Booléen (boolean)` : Représente une valeur vraie (true) ou fausse (false).
```php
<?php
$estConnecte = true;
?>
```

- `Tableau (array)` : Représente une collection d'éléments.
```php
<?php
$courses = array("Tomates","Sel","Poivre","Huile");
?>
```

- `Null` : Représente l'absence de valeur.
```php
<?php
$vide = null;
?>
```
- `Objet (object)` : Représente des instances de classes.
```php
<?php
class Personne {
    public $nom;
    public $age;
}
$personne1 = new Personne();

?>
```


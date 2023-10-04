# LES ENTIERS
En PHP, le type de données "integer" est utilisé pour représenter des nombres entiers, c'est-à-dire des nombres sans partie décimale. Les entiers peuvent être positifs ou négatifs.

## Déclaration de variables "integer"
Pour déclarer une variable de type `integer` en PHP, utilisez `le signe dollar ($) suivi du nom de la variable et de l'opérateur d'attribution (=)` pour lui assigner une valeur entière.
```php
<?php
$age = 25; // Déclaration d'une variable $age de type integer avec la valeur 25
$nombreNegatif = -10; // Un entier négatif
?>
```

## Opérations arithmétiques :
Vous pouvez effectuer diverses `opérations arithmétiques` avec des variables de type "integer", telles que `l'addition`, `la soustraction`, `la multiplication`, `la division`, etc.
```php
<?php
$a = 10;
$b = 5;

$addition = $a + $b; // Addition ($addition contient 15)
$soustraction = $a - $b; // Soustraction ($soustraction contient 5)
$multiplication = $a * $b; // Multiplication ($multiplication contient 50)
$division = $a / $b; // Division ($division contient 2)
?>
```

## Conversion en "integer"
Si vous avez une chaîne de caractères contenant un nombre entier, vous pouvez la convertir en un entier en utilisant la fonction `intval()`.
```php
<?php
$chaine = "42";
$entier = intval($chaine); // Conversion de la chaîne en un entier ($entier contient 42)
?>
```

## Vérification du type de données
Pour vérifier si une variable est de type "integer", vous pouvez utiliser la fonction `is_int()`.
```php
<?php
$nombre = 123;
if (is_int($nombre)) {
    echo "La variable est un entier.";
} else {
    echo "La variable n'est pas un entier.";
}
?>
```

## Qu'est-ce la POO ?
La POO repose sur le concept d'objets. Dans le monde réel, un objet est une instance d'une classe, par exemple, une voiture, un chien, une personne, etc. En POO, une classe est un modèle qui définit les caractéristiques (propriétés) et les actions (méthodes) que les objets de cette classe auront.

## Classes en PHP
En PHP, une classe est définie à l'aide du mot-clé `class`. Pour créer une classe en PHP, utilisez le mot-clé `class`, `suivi du nom de la classe`, et `ouvrez des accolades pour définir le contenu de la classe`. `À l'intérieur de la classe, vous pouvez déclarer des propriétés (variables) et des méthodes (fonctions)`.
Voici un exemple simple de définition d'une classe "Personne" avec des propriétés `(nom et âge)` et des méthodes `(direBonjour et direAge)`
```php
<?php
class Personne {
    // propriétés
    public $nom;
    public $age;

    // méthodes
    public function direBonjour() {
        echo "Bonjour !";
    }
}
?>
```
Dans l'exemple ci-dessus, nous avons créé `une classe nommée Personne` avec `deux propriétés` : `$nom` et `$age`, ainsi qu'une `méthode direBonjour` qui affiche un message de salutation.

## Instanciation d'objets
Pour utiliser une classe, vous devez créer une `instance (un objet)` de cette classe. 
Une fois que vous avez défini une classe, vous pouvez créer des `objets` à partir de cette classe. Vous pouvez le faire en utilisant l'opérateur `new`
- 1
  ```php
  <?php
    $jhon = new Personne();
  ?>
  ```
  Cela crée un objet `$john` basé sur la classe "Personne". 
  Vous pouvez accéder aux `propriétés` et `méthodes` de cet objet en utilisant l'opérateur `->`. Par exemple, pour définir le nom de la personne et appeler la méthode `direBonjour`:
  ```php
  <?php
    $john->nom = "John";
    $john->direBonjour(); // Affiche "Bonjour !"
  ?>
  ```
  `Les propriétés` sont accessibles avec `$objet->propriete` et `les méthodes` sont appelées avec `$objet->methode()`.

- 2
  ```php
  <?php
    $personne1 = new Personne();
    $personne2 = new Personne();
  ?>
  ```
  Maintenant, vous avez `deux objets`, `$personne1` et `$personne2`, qui sont des `instances de la classe "Personne"`.

## Utilisation de constructeurs
Il est courant d'utiliser un `constructeur` pour `initialiser les propriétés d'un objet lorsque celui-ci est créé`. Le constructeur est une méthode spéciale appelée `__construct`
```php
<?php
  class Personne {
    public $nom;
    public $age;

    public function __construct($nom, $age) {
        $this->nom = $nom;
        $this->age = $age;
    }

    public function direBonjour() {
        echo "Bonjour, je m'appelle " . $this->nom;
    }
}
?>
```
Ainsi, lorsqu'un objet est créé, `vous pouvez passer des valeurs au constructeur pour initialiser ses propriétés`.
```php
<?php
  $personne1 = new Personne("John", 25);
  $personne1->direBonjour(); // Affiche "Bonjour, je m'appelle John"
?>
```

## Héritage et encapsulation en POO
L'héritage et l'encapsulation sont deux concepts importants de la programmation orientée objet (POO) en PHP. Ils permettent de créer des structures de code modulaires et réutilisables en organisant les classes et en contrôlant l'accès aux propriétés et aux méthodes.

  ### Héritage
  L'héritage est un mécanisme qui permet à une classe (appelée classe fille) d'hériter des propriétés et des méthodes d'une autre classe (appelée classe parente). Cela favorise la réutilisation du code et la création de hiérarchies de classes.
  * Supposons que nous ayons une classe parente "Véhicule"
    ```php
      <?php
        class Vehicule {
            public $marque;
            public $annee;

            public function demarrer() {
                echo "Le véhicule démarre.";
            }
        }

      ?>
    ```
  * Nous pouvons ensuite créer une classe fille "Voiture" qui `hérite des propriétés et des méthodes` de la classe "Véhicule"
    ```php
      <?php
        class Voiture extends Vehicule {
            public $modele;

            public function klaxonner() {
                echo "La voiture klaxonne.";
            }
        }

      ?>
    ```
  Avec `l'héritage`, `la classe "Voiture" a accès aux propriétés et méthodes de la classe "Véhicule" en plus de ses propres propriétés et méthodes`. Cela permet de créer des classes spécialisées tout en réutilisant le code de base.

  ### Encapsulation
  `L'encapsulation` est un concept qui consiste à `restreindre l'accès aux propriétés et méthodes d'une classe`. 
  ```
  La POO encourage l'encapsulation, ce qui signifie que les propriétés d'un objet devraient normalement être définies comme privées (ou protégées) pour empêcher un accès direct depuis l'extérieur de l'objet. Vous utilisez ensuite des méthodes (getters et setters) pour accéder ou modifier ces propriétés de manière contrôlée.
  ```
  En PHP, vous pouvez définir la portée des propriétés et des méthodes en utilisant des `modificateurs d'accès`. Les modificateurs courants sont `public`, `private`, et `protected`.
  * `public` : Les propriétés et les méthodes sont accessibles de partout.
  * `private` : Les propriétés et les méthodes sont accessibles uniquement depuis la classe où elles sont définies.
  * `protected` : Les propriétés et les méthodes sont accessibles depuis la classe où elles sont définies et depuis les classes filles.
  
  Dans la classe "Véhicule", vous pouvez `définir des propriétés comme privées` pour `les protéger de l'accès direct depuis l'extérieur de la classe`
  ```php
    <?php
      class Vehicule {
        private $marque;
        private $annee;

        public function __construct($marque, $annee) {
            $this->marque = $marque;
            $this->annee = $annee;
        }

        public function getMarque() {
            return $this->marque;
        }

        public function getAnnee() {
            return $this->annee;
        }
    }
    ?>
  ```
  Vous pouvez ensuite utiliser des méthodes `getters` (comme `getMarque` et `getAnnee`) pour `accéder aux propriétés de manière contrôlée`.

## Méthodes magiques
Les méthodes magiques, également appelées `méthodes spéciales`, sont des `méthodes prédéfinies` en PHP qui `commencent par deux caractères de soulignement (_) suivis d'un nom de méthode`. Ces méthodes magiques sont automatiquement appelées dans certaines situations spécifiques lorsqu'elles sont définies dans une classe. Elles permettent de `personnaliser le comportement de la classe en réponse à certaines actions`. Voici quelques-unes des méthodes magiques les plus couramment utilisées en PHP :
* `__construct()` : Cette méthode est le `constructeur de la classe`. Elle est `appelée automatiquement lorsqu'un nouvel objet de la classe est instancié`. C'est un `endroit idéal pour initialiser des propriétés ou effectuer d'autres tâches d'initialisation`.
  ```php
      <?php
        class MaClasse {
          public function __construct() {
              // Code d'initialisation
          }
        }
      ?>
  ```
* `__destruct()` : Le destructeur est `appelé automatiquement lorsque l'objet est détruit ou lorsqu'il n'est plus utilisé`. Vous pouvez l'`utiliser pour effectuer des tâches de nettoyage, comme la fermeture de connexions ou la libération de ressources`.
  ```php
    <?php
      class MaClasse {
        public function __destruct() {
            // Code d'initialisation
        }
      }
    ?>
  ```
* `__toString()` : Cette méthode est `appelée lorsque l'objet est converti en une chaîne de caractères` à l'aide de la fonction `echo` ou `print`. Vous pouvez la définir pour renvoyer une `représentation sous forme de chaîne de l'objet`.
  ```php
    <?php
      class MaClasse {
        public function __toString() {
          return "Ceci est une instance de MaClasse";
        }
      }
    ?>
  ```
* `__get()` et `__set()` : Ces méthodes sont `utilisées pour accéder aux propriétés d'un objet` ou pour `modifier les propriétés inaccessibles directement`. Par exemple, si vous avez déclaré des propriétés privées ou protégées, vous pouvez personnaliser la manière dont elles sont obtenues ou définies.
  ```php
    <?php
      class MaClasse {
        private $valeur;

        public function __get($nom) {
            if ($nom === 'valeur') {
                return $this->valeur;
            }
        }

        public function __set($nom, $valeur) {
            if ($nom === 'valeur') {
                $this->valeur = $valeur;
            }
        }
      }
    ?>
  ```
* `__call()` : Cette méthode est `appelée lorsque vous tentez d'appeler une méthode qui n'est pas définie dans la classe`. Vous pouvez personnaliser le comportement lorsque des méthodes inexistantes sont appelées.
  ```php
    <?php
      class MaClasse {
        public function __call($nom, $arguments) {
          echo "La méthode $nom n'existe pas.";
        }
      }
    ?>
  ```


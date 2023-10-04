# Qu'est-ce qu'une session ?
Une session est une façon de stocker temporairement des informations spécifiques à un utilisateur sur le serveur web. Chaque utilisateur de votre site web se voit attribuer une session unique lorsqu'il visite votre site.

# Pourquoi avons-nous besoin de sessions ?
Les sessions sont utiles pour stocker des informations sur un utilisateur tout au long de sa visite sur un site web. Par exemple, vous pouvez utiliser des sessions pour garder une trace de l'identité d'un utilisateur connecté, pour stocker des paniers d'achats temporaires, ou pour stocker des préférences de l'utilisateur.

# Comment fonctionnent les sessions en PHP ?
En PHP, les sessions sont gérées par le biais d'un identifiant de session unique (appelé souvent "session ID") qui est généralement stocké dans un cookie sur l'ordinateur de l'utilisateur. Ce cookie permet d'associer l'utilisateur à une session spécifique sur le serveur.

# Création d'une session :
Pour créer une session en PHP, vous devez d'abord appeler la fonction `session_start()` au début de votre script PHP. Cela initialise la session ou reprend une session existante si elle existe déjà.
<?php
session_start();
// Le reste de votre code
?>

# Stockage de données dans une session :
Vous pouvez stocker des données dans une session en utilisant la superglobale `$_SESSION`. Par exemple, pour stocker le nom d'utilisateur d'une personne connectée :
<?php
$_SESSION['nom_utilisateur'] = 'JohnDoe';
?>

# Récupération de données de session :
Pour récupérer des données de session, utilisez `$_SESSION` :
<?php
$nom_utilisateur = $_SESSION['nom_utilisateur'];
?>

# Fermeture de la session :
Vous pouvez fermer une session en utilisant `session_destroy()` lorsque vous n'avez plus besoin de stocker des données de session.
<?php
session_destroy();
?>
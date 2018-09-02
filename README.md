# Mettre en œuvre une solution de gestion de contenu ou e-commerce.

Il existe plusieurs solutions d'ecommerce. 

Le langage où on en trouve plus, aujourd'hui, est PHP (Prestashop, Drupal Commerce, WooCommerce, Magento, Sylius, etc.).

## Les fonctionnalités de bases

Chaques solutions possèdent leurs avantages et inconvénients, mais toutes doivent avoir le minimum :

* Le catalogue produits avec la possibilité d'ajouter, modifier et d'en supprimer
* Ranger les produits par catégories
* le système de panier
* Gestion des tarifs de livraisons
* La page de récapitulatif de l'achat (produits achetés, quantité, tarifs livraisons)
* Intégrer un système de paiement simplement
* Création de factures
* Espace utilisateur

La solution choisit doit pouvoir permettre d'ajouter de nouvelle fonctionnalité (modules, plugins)

# Drupal Commerce

[Drupal Commerce](https://drupalcommerce.org/) est une suite de modules pour ajouter les fonctionnalités e-commerce au CMS [Drupal](https://www.drupal.org/).

L'intérêt d'utiliser Drupal & Drupal Commerce  est que vous pouvez créer et personnaliser votre site e-commerce sans avoir besoin d'une connaissance poussées de PHP. HTML/CSS, un peu de [Twig](https://twig.symfony.com/) et votre bon sens suffiront.

## Stack

Avant d'installer, il faut avoir le minimum.

* PHP 7
* MySQL 
* git
* Nginx / Apache
* [Composer](https://getcomposer.org/download/) le gestionnaire de dépendance de PHP.

Optionnel : Composer est lent. Vous pouvez augmenter sa rapidité en utilisant le plugin [Pretissimo](https://github.com/hirak/prestissimo) (Après avoir installé Composer)

## Installation 

Il y a plusieurs manières d'installer Drupal Commerce. Nous allons utiliser l'[installation par Composer](https://docs.drupalcommerce.org/commerce2/developer-guide/contributing/setup-local-environment#getting-commerce).

Cela va nous permettra de laisser la gestion des dépendances à composer.

## Personnalisations

### Modules(extensions)

Il manque des fonctionnalités. Heureusment, qu'il y a le système de plugin de Drupal.

**Note : Installer les modules et extensions toujours en utilisant composer.**

Vous pouvez-même récuperer des modules directement sur le site officiel de [Drupal](https://www.drupal.org/project/project_module). Il ne faut pas oublier de préfixer 
vos commandes d'installation  via composer par le terme *drupal/*. Sinon, le module ne sera pas trouvé.

Exemples : 

Pour installer le module [Pathauto](https://www.drupal.org/project/pathauto) Récupérer le nom du module de l'url. Pour cela, récupérer le terme qui se trouve après la partie *project/* de l'url. Dans notre cas **pathauto** (*https://www.drupal.org/project/**pathauto***) 

```console
composer install drupal/pathauto
```

### Thème 

Vous pouver créer votre propre thème, mais le plus facile c'est de partir d'un thème existant et de surcharger les parties qui nous intéressent. 

Concrètement il faut créer un [thème enfant](https://www.drupal.org/docs/8/theming-drupal-8/creating-a-drupal-8-sub-theme-or-sub-theme-of-sub-theme) qui dépend du thème qu'on veut modifier, puis on copie le fichier template que l'on veut surcharger du thème parent vers le thème enfant.

# A vous de jouer 

La marque Patatèr veut se moderniser et vendre ses baskets sur internet. Cette marque est spécialisée dans les chaussures de villes mais proposent aussi des modèles sport. Voici la liste des types de chaussures qu'elles proposent : 

* Ville homme/femme
* Sport homme/femme
* Enfant garçon/fille

Les baskets sont disponibles en plusieurs couleurs et plusieurs tailles (du 36 au 50).

Vous devez créer le site e-commerce :

* En tant que commerçant je veux ajouter les chaussures afin de les afficher sur le site
* En tant que commerçant je veux gérer les catégories afin  de pouvoir en ajouter dans l'avenir
* En tant que commerçant je veux gérer les tailles afin  de pouvoir en ajouter dans l'avenir
* En tant que commerçant je veux pouvoir gérer les frais de ports 
* En tant que client je veux passer une commande pour recevoir le produit voulu
* En tant que client je veux voir la liste des commandes que j'ai passé

**Bonus** :

* Ajouter différernts moyens de livraisons avec différents tarifs
* Ajouter le système de réduction

## Contraintes

* Installer un module 
* Personnaliser le thème. CSS mais aussi markup (pour le markup juste une partie suffit)
* Mettre en place le paiement de sandbox de paypal
* Site responsive

## A rendre

Screenshots des pages: 

* produits 
* détails d'un produit
* panier
* récapitulatif du panier
* détails compte utilisateur
* liste des commandes pour un utilisateur
* liste de toutes commandes passées sur le site
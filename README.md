# DoctoRIF
# Angular + Spring boot + micro services + PostgreSQL 

## Description
La conception et la réalisation d’une application web s'applle `DoctoRIF`, c'est une application qui va permettre de connaître les medecins dans toutes les villes de la tunisie et avec différentes spécialités.

## Architecture
L'application est devisée en deux parties, une partie backend `Spring boot + micro services` et une partie frontend avec `Angular`. 

## Les modules réalisés :
* Gestion des utilisateurs (Admin, Docteur, client ).

## Backend
Le côté backend est composé d'applications Spring Boot organisées selon l'architecture du micro service.
Voici une image qui illustre l'architecture de l'application : 
![](img/architecture.PNG?raw=true)

Il y a quelques micro services : 

### Liste des micro services :
* 1 er micro service `ConfigurationService` : c'est un micro service qui contient un fichier de configurations, il est lié à un dossier de config sur git.
* 2 ème micro service `ServiceDiscovery` : c'est un micro service qui contient toutes les informations de tous les autres micro services `up/down`...
* 3 ème micro service `ServiceGateway` avec `Zull` : Il joue le rôle d'un proxy; c'est la première porte pour utiliser l'application. Il fait aussi la gestion de `l’authentification`.
* 4 ème micro service `UserManagement` : Ce micro service est destiné pour faire la gestion des utilisateurs (`Administrateur`, `Docteur`, `Patient`)de l'application ``DoctoRIF``.
* Un dossier git pour la configuration : un dossier `Git` contient les configurations du projet. Il est lié au micro service `ConfigurationService`.
Ceci est un lien vers ce dossier git qui contient la configuration ==> 
[Configuration Git](https://github.com/ramzid/doctorifConfigurationbackend) 

## Comment exécuter le projet 
* 1 ère chose : exécutez le service `ConfigurationService` en premier lieux, en cliquant à droit sur le service puis sur le bouton `run`.
* 2 ème chose : exécutez le service `ServiceDiscovery`, en faisant la même chose que le premier.
* 3 ème chose : exécutez le service `ServiceGateway`.
* 4 ème chose : exécutez le service `UserManagement`.
* Allez dans votre navigateur et tapez `http://localhost:8761/`, une page comme cela va apparaître.
![](img/services.PNG?raw=true)
Elle contient un tableau avec la liste de micro services lancés avec l'adresse et le port de chaque micro service.

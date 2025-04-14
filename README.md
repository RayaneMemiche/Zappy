# B-YEP-410-PAR-4-1-zappy-pierre-alexandre.delgado-arevalo

# Le projet

L'objectif de ce projet est de créer un jeu vidéo en réseau, dans lequel ce ne sont pas des humains qui jouent, mais des IA.

Les IA qui se connectent rejoignent toutes une équipe de leur choix.

Pour gagner une partie, une équipe doit avoir 6 de ses joueurs avec le niveau 8.

Le monde, appelé Trantor est une planète où toutes les 20 unités de temps (ici 1 unité de temps = 1 seconde),

des ressources sont placées sur chaque parcelle du terrain.

Les ressources sont les suivante:

Pour survivre:
```
food
```
Pour évoluer:
```
linemate
deraumere
sibur
mendiane
phiras
thystame
```


## Le serveur

Le serveur, écrit en C, a pour objectif la communication avec les clients IA et clients graphique.

Il a aussi pour objectif de stocker les données et de gérer les demandes faites par les clients par rapport au jeu (se déplacer, évoluer...)

Pour exécuter les actions envoyées par les clients, le serveur devra attendre un certain temps (défini dans les parties respectives des clients)

Les clients n'ont pas besoin d'attendre une réponse du serveur avant de renvoyer des commandes, le serveur les stockera et les executera a la suite 

des autres commande, sauf pour le client graphique, où il n'y a pas de limite pour les commandes.

Chaque commande envoyé en plus seront ignorées par le serveur

### Lancer le serveur
Compilation:

```
make
```
ou
```
cd zappy_server
make
```

Lancer le binaire:
```
USAGE: ./zappy_server -p port -x width -y height -n name1 name2 ... -c clientsNb -f freq
  port      is the port number
	width     is the width of the world
	height    is the height of the world
	nameX     is the name of the team X
	clientsNb is the number of authorized clients per team
	freq      is the reciprocal of time unit for execution of actions
```

## L'ia

Les IA, codé en C++, ont pour premier objectif de survivre, en récupérant de la nourriture sur chaque parcelle du monde.

Elles peuvent s'entraider en communiquant entre elles et en déposant leurs propres ressources sur le sol.

Leur second objectif et le plus important pour gagner est de monter au niveau 8, en mettant les pierres demandées dans la même parcelle et en lançant l'incantation

### Lancer une IA

La compilation:
```
make
```
ou
```
cd ai_cli
make
```
Lancer le binaire:
```
USAGE: ./zappy_ai -p port -n name -h machine
	port	is the port number
	name	is the name of the team
	machine	is the name of the machine; localhost by default
```

## Le graphique

Le graphique, fait avec unity, a pour unique objectif d'afficher l'état actuel de la partie, avec les map et les joueurs exécutant leurs actions

```
screenshot graphique
```
### Lancer le graphique

La compilation:
```
make
```
Lancer le binaire:
```
USAGE: ./zappy_gui
```
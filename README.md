# The Project

The objective of this project is to create a network-based video game in which it is not humans who play, but AIs.

The AIs that connect all join a team of their choice.

To win a game, a team must have 6 of its players reach level 8.

The world, called Trantor, is a planet where every 20 time units (here 1 time unit = 1 second),
resources are placed on each tile of the terrain.

The resources are as follows:

For survival:
```
food
```
For evolution:
```
linemate
deraumere
sibur
mendiane
phiras
thystame
```


## The Server

The server, written in C, aims to communicate with AI clients and graphical clients.

It also aims to store data and manage requests made by clients with respect to the game (move, evolve, etc.)

To execute the actions sent by clients, the server must wait a certain time (defined in the respective client sections)

Clients do not need to wait for a response from the server before sending new commands; the server will store them and execute them in sequence with the other commands, except for the graphical client, where there is no limit for commands.

Any additional commands sent will be ignored by the server.

### Running the Server
Compilation:

```
make
```
or
```
cd zappy_server
make
```

Run the binary:
```
USAGE: ./zappy_server -p port -x width -y height -n name1 name2 ... -c clientsNb -f freq
  port      is the port number
	width     is the width of the world
	height    is the height of the world
	nameX     is the name of team X
	clientsNb is the number of authorized clients per team
	freq      is the reciprocal of the time unit for execution of actions
```

## The AI

The AIs, coded in C++, have the primary objective of surviving by collecting food from each tile of the world.

They can help each other by communicating and by placing their own resources on the ground.

Their second objective, and the most important one to win, is to reach level 8 by placing the requested stones on the same tile and starting the incantation.

### Running an AI

Compilation:
```
make
```
or
```
cd ai_cli
make
```
Run the binary:
```
USAGE: ./zappy_ai -p port -n name -h machine
	port	is the port number
	name	is the name of the team
	machine	is the name of the machine; localhost by default
```

## The Graphical Client

The graphical client, made with Unity, has the sole objective of displaying the current state of the game, with the maps and players executing their actions.

```
screenshot graphic
```
### Running the Graphical Client

Compilation:
```
make
```
Run the binary:
```
USAGE: ./zappy_gui
```

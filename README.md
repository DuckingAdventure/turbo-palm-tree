# Functional Specification

This should be a Work In Progress document with minimum information to start code the game. More features can be added later once the game takes form.

## Contents

- [Index](#turbo-palm-tree)
    - [Game Mechanics](#game-mechanics)
        - [Core Gameplay](#core-gameplay)
        - [Gameflow](#gameflow)
    - [Gameplay Elements](#gameplay-elements)
        - [Rooms](#rooms)
        - [Weapons](#weapons)
        - [Stat Upgrade](#stat-upgrade)
        - [Enemies](#enemies)
        - [Boss](#boss)
    - [Game Physics](#game-physics)
        - [Player](#player)
        - [Enemies](#enemies)
        - [Boss](#boss)
    - [Level Requirements](#level-requirements)

## Game Mechanics

#### Core Gameplay

* A top down game with a fixed camera
* Player with a Simple Stat System(Health, Damage)
* Enemies with Steering Behavior to chase down the player
* Enemies can drop Loot(Weapons, Stat Upgrade)
* Level that is consisted of "Rooms" connected to each other. Enemies can only move within their own Room
* Weapon System where the player can replace current weapon with a new one by picking it up as loot
* Boss Room
* Player can move freely to any room except the Boss Room

#### Gameflow

The game world consists of rooms that are connected to each other. The camera is fixed in a top down style and follows the player. The rooms are different from each other and can contain enemies or loot in the form of items or status power ups. The player start in an empty "starting" room at the start of the game session is able to freely enter any of the rooms except for the room which contains the Boss enemy. To complete the level the player must find a way to gain access to the Boss room and slay the Boss enemy. Enemies in the rooms will chase the player within the room they belong to and have a chance to drop loot upon death.

## Gameplay Elements

#### Rooms
There are Different rooms that the Level Designer can use.

* Room with enemies
* Starting room for the player to start
* Boss Room

The visibility in the rooms can be adjusted with shading(lower ambient light), dynamic shadows and light sources

#### Weapons

* Spear - a forward thrust weapon
* Sword - wider range than Spear

The player starts with the Spear and can replace it by picking up other weapons when they drop as loot.

#### Stat Upgrade

The player starts with 2 health and can pick up more when they drop as loot.

#### Enemies

Enemies with Steering Behavior that will chase down the player. If the Enemy manages to inflict damage to the player 1 health is substracted from the player. The player is able to damage the enemies and they despawn after two hits and has a chance to drop Loot(Weapons, Stat Upgrade)

#### Boss
The Boss will teleport to the player's location and execute one of his attacks in a telegraphed way.

* Skill Placeholder 1
* Skil Placeholder 2
* ...

## Game Physics

#### Player

The player is controlled with Keyboard and/or Mouse. Experiment with keybindings to find a good layout. Player physics body will collide with Room, Enemies, Boss. Upon getting damaged by enemies or boss the player will be pushed back(knock back) by applying a force to the physics body.

#### Enemies

Enemies are controlled by a variety of Steering behaviors and will have the player as target. The enemy entity will be pushed back(knock back) if the player damages them.

#### Boss

The boss has the player as target and will use its programmed attacks to try and inflict damage. The boss is not affected by knockback upon damage.

## Level Requirements

Level 1 has an empty starting room for the player to start its game session and a few connected rooms placed out with enemies. Enemies in the room are endlessly spawning. To access the Boss Room the player must kill enemies to find the key.

Killing the Boss ends the game.

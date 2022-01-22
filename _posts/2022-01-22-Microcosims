---
title: A Procedural World is Born
published: true
---

# [](#microcosims)Microcosims
I started this project to learn C++ and after a few months I am starting to get the hang of it. My interests tend to jump around, so when I started writing the first lines of code I was not sure if I would get bored with the language after two weeks. With that in mind, I decided to focus on the main elements of a city-builder I always wanted to understand: units collecting and storing resources on a map. 

Raylib, a flexible game-making library written in C that can be built cross platform and even run on the web, fits the type of framework I prefer, one that provides exactly what is needed, no more, no less. However, that means it is up to me as the developer to write nearly everything from scratch. What is a unit? How does it get from one point on a 2D map to another? How does a player define a storage area? How does the program even know what to do when a player clicks the mouse? All of these problems (and maaaaaany more) are systems I needed to design. A few months into this project, I can safely say that I did not get bored trying to solve all of these problems, and I'm excited to continue.

## [](#what-has-been-built)What has been built?

![](https://github.com/nullreference8/nullreference8.github.io/blob/main/assets/2022-01-22-chop-tree.gif?raw=true)

Each unit has a job queue and an inventory. A job is made up of a series of tasks that must be completed in order to move on to the next task. Let's break down the job that chops down a tree and stores a log into its tasks. The job is created after a player designates a tree to be chopped and a unit capable of performing the job is found by the game engine. 

#### [](#chop-tree-job)Chop Tree Job
1. Assign the unit's target location to the location of the selected tree
2. Find a path to the target tree, avoiding unpassible terrain
3. While the unit's target location is not the unit's current location, move the unit according to its movement speed along the path
4. When the unit is positioned at its target location, deconstruct the resource at that location and put the yeilded items into its inventory

Now the unit has chopped down the tree and has stored the resulting logs in its inventory. The chop tree job is complete, but now the unit needs to store those items. If the player defines an area for storage and enables resources to be stored in that area, the game engine will search for units holding items, or items available freely across the map, and issue a job to the unit to deposit the item in an available square.

#### [](#store-item-job)Store Item Job
1. Assign the unit's target Location to the location of the selected open storage square
2. Find a path to the target square, avoiding unpassible terrain
3. While the unit's target location is not the unit's current location, move the unit according to its movement speed along the path
4. Remove the item from the unit's inventory and place it in the square's inventory

This is the level of detail required in order to do even the most simple things when building a game. I have even glossed over a number of complexities here like the user interface, defining keyboard and mouse input, and the entire inventory and item system. You might have even noticed the error at the end of the little sample above (that I've since fixed). 

## [](#next-steps)Next Steps
With the basic goal I set for myself completed, two main things are on the to-do list. First, I need to generate a basic map procedurally with resouces for units to collect. The core component of this project is building a procedurally generated world, so this step will take a significant amount of time, research, and effort. I know almost nothing about procedural generation, so it will be as challenging as getting started with C++. From my early searching it seems that much of the knowledge in this area is written in the form of research papers, not code examples, so that will be an additional hurdle. Second, I'll need a way to store the generated map and the state of everything I wrote about above. For this I will use a locally stored relational database, SQLite3. All of the components I wrote about above will need to be directed to the database file instead of system memory where they currently reside. 

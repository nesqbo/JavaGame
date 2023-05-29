# JavaGame
GAME ENGINE


OVERVIEW
My game has been inspired by real life maze-like parks. 
For the purpose of this game, I have added monsters which the player fights with. I have also added japanese sake which is drank as soon as the player collides with it to up their characters health. There are also some keys that can be picked up. The picked-up keys are stored in the inventory until there are enoough and the player reaches doors which can only be opened after the specified amount of monsters is killed and all the keys have been collected. 
That´s it for how the game works.
To load data from a previous game, you will need to click on the Load from file button which loads previous amount of killed monsters, position X and Y from when the game was last saved, amount of picked up keys and hearts. Note that it only loads data that has been EXPLICITLY saved by clicking on the Save button.  You can load your saved game as many times as you want during your play.

To save your current game data so you could return to your game state later, you will need to click on the Save button which saves your CURRENT data.You can save your data however many times you want, note that only the LASTEST data from the latest click on the button will be saved. No rewinds of the data will be possible.

There are many maps the player can choose to play on. However, the map02 is a default one. If you want to change it, you have to click on the Level button.

FIGHTING MONSTERS
ABOUT MONSTERS - The monsters move at random, so do your best to catch and kill them!
To initiate a fight with a monster, you will need to collide with it. You cannot end the game without killing a specified amount of monsters.

PICKING UP OBJECTS
You can pick up a bottle of japanese sake or a key.
 The amount of keys you've picked up so far will be stored on the top of the screen.
Once you pick up a bottle of japanese sake, your player will consume it immediately if their heart amount is lower than the maximum. Otherwise, the player won't be able to pick up the bottle at all.

WINNING THE GAME
To win the game, you must kill a specified amount of monsters and have a specified amount of keys collected. Otherwise the door won't open, which will mean that you haven't won.

PROGRAMMERS VIEW
There are three packages with different classes and there are also two other classes..
- Entities - Food, Key, Monster, Player
- Main - Main
- Models - Listener, LoadSave, MapModel, MonsterService, ObjectService, PlayerService 
- others - MainPanel, Stats
The food class is a class which mainly specifies the attributes of the Food object. It constructs the object and gets it image.

The Key class is a class which constructs the Key object and loads it image.

The Monster class is a class which constructs the Monster entities and loads their images. It also updates the monster moves.

The Player class is a class which constructs the Player entity and loads its image. It also includes an update method which is connected to the listener thanks to which it's able to catch pressed keys and move the player accordingly.


The Listener class extends the KeyListener class and catches the user's pressed and released keys which are stored in private variables that are accessed with getters to help the player move on the frame.

The LoadSave class extends the JPanel class. It constructs all the buttons that are visible on the frame and has actionListeners implemented so when each of the button is pressed, the frame is updated accordingly.
It has three buttons: Load from file, Save and Level

The first button loads previously saved data from a json file to the screen
The second button saves the users current stats for later loading
The last button loads the map according to the one that is chosen by the user
Other than this, the method also includes private helping methods and a default map reading method that reads a default map if none has been specifically chosen yet.


The MapModel class's main purpose is for drawing out the map board on the frame. It loads all the tile pictures and paints them out based on how the matrix is composed in each of its respective files.

The MonsterService class takes care of the collisions of the monsters with the borders of the map board. It also handles collisions with the player.

The ObjectService class is a class which takes care of the player's collisions with all objects. (keys and bottles)

The PlayerService class is a class which takes care of all the Player's collisions within the map and its borders.

The MainPanel class extends the JPanel. It is the main view class in my project. It is the centre of this whole game. There is a game loop and thread created and implemented every game. It also includes methods update and repaint which update the stats of the game and based on them, are later being drawn out on the frame.

The Stats class only includes the constructor which takes in the players stats and then uses the draw method to draw them out on the frame. They are the stats right bellow the buttons and above the game board.

MVC
The MVC structure in this project is as follows:
- MODELS: Listener, LoadSave, MonsterService, ObjectService, PlayerService
- VIEW: Food, Key, Monster, Player, MapModel, MainPanel and Stats
- I have not implemented a controller as I wasn't too familiar with it and the concept confused me a little

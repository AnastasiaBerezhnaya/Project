The Game of Clans
======


| Product name       | The Game of Clans |
| ------------- | :------------- | 
| **Team name**  | **BAZE.team** |
| **Team members**    | **Anastasia Berezhnaya**,**Edgar Zhuzhin**     |   
| **Date of report** | **06.12.2013**     |   


1. Introduction
======

*Overall description of the project, context*


GamesInc. is about to start new entertainment project “the Game of  Clans”. The Game of Clans is team recreational game activity where players attempt to score points by making a strategy to capture the enemy’s treasure. There is special large playing area.
Our purpose is to develop smartphone application to support the game process. 


*Overall description of the system*


Our system will be based on indoor positioning and involved in game process. From the beginning all members of the team get a gadget (iOS, Android or Windows Phone), also they can use their own gadget to install the game app beforehand. With this app teams choose a Clan they will play for (application offers various choices). Depending on their choice there will be different user interface themes. Game process is based on tracking the enemies on a map. On the map there will be several blind spots that hide players from enemies. Victory occurs when one or more of alive team members find a treasure of opponent team. More precisely the game process will be described further.

2. Use cases
======

*Definition of the user groups*


| User group       | Brief defenition |Defenition |
| ------------- | :------------- | :------------- |
| Player | Normal team member |Active team player in the game uses application to recognize the location of enemies and find the treasure. |
| Commander    | Leader of the team     | Has some privileges and special role in the game. Commander makes the strategy of attack and can direct the players.  |



*Use cases*    
 
**Player**
  
* Choose workspace (theme)
* Enter name 
* Become commander 
* Shoot 
* Reload weapon  
* Track enemies 
* Use bonus 
* Find treasure 
* See rest of the time 
* See commands 
* See life parameters 

**Commander**  

* Choose workspace (theme)
* Enter name
* Shoot
* Reload weapon
* Track enemies
* Give commands
* Direct players
* Approve bonus
* See rest time
* Find treasure
* See life parameters     



*Use case diagram*

![myflowcart](http://users.metropolia.fi/~zhuzhine/Software/UseCase.jpg)


*Use case scenarios (based on template)*

 
**Use Case ID:**	1	   
**Use Case Name:**	Find treasure	   
**Actors:**	Player	   
**Description:**	Player accessed the game and finds the treasure	   
**Preconditions:** 
* Player has started the game
* Player has logged in certain workspace
* Player has entered name

**Post conditions:**

* Player got the treasure
* Player’s team won (Victory notification)	

**Normal Flow:**	   
* Find the treasure
* Player got location and game map
* Player got commands 
* Player follow
* Observe the map
* Shoot enemies
* Notice that treasure radar became «warmer»
* Get closer
* Got treasure

**Alternatives Flow:**
* Find the treasure
* During the game process player got killed (after p. 4-5 1.0)
* Send a request to commander to use “Undead” bonus
* Bonus approved
* Get to the treasure in 2 min
* Got treasure


*Depiction of one use case as a flow chart*

![myflowcart](http://users.metropolia.fi/~zhuzhine/Software/Flowchart1.jpg)


3. System architecture
======

*High-level overview of the system*

The Game of Clans is a multi-player networked game application. Software is installed on device, providing users interaction within the same virtual
enviroment. The game engine is responsible for presenting the game to the player and for receiving player inputs.The simulation is responsible for updating the state of the virtual game world in response to player inputs and the rules of the game and virtual world. The object system is responsible for maintaining the state information describing all objects in the game.

![myflowcart](http://users.metropolia.fi/~zhuzhine/Software/Untitled.png)



*Main modules and their functions represented*

* The simulation component of the game is processed on the server.
* Interface of the game engine is processed on the devices of the players.
* The object system is designed to keep all data between interface and other components in order to implement system.
* Data manager manages storage and retrieval of game state for load game functionality.
* The simulation control module receives player input information from the game engine and passes it to the control function.
* Game logic realizes the rules of game.
* Game engine is designed as tracking map with player's interface.
* The functional components, the game engine, the simulation and the data manager all interact with the object system.


4. Requirements 
======
 
*Functional requirements*

- Game.startScreen: The user, who got a device, can select workspace – “clan” and the game will proceed in the chosen theme.
- Game.login: The player logins, entering username in given form. 
- Game.playermode: The user has an option to select between playing a game as basic character or in commander mode.
- Game.commander: Before players of each team negotiate in advance who is going to be their commander in the game. But in a case of two players from one team chose the commander mode, the first one, who selected it, enters in game as commander. Second one receives a message that the commander mode is already is taken. 
- Game.start: The user proceeds to game’s tracking map.
- Player.combonus: The commander receives messages from other players from the team with requests with permission to use bonuses they got.
- Player.comguide: The commander can guide other players from a team by dragging points on tracking map.
- Player.shoot: Device is used as weapon in the game. When player shoots, is showing how many charges left.
- Player.gotshoot: Player, who got shoot in the game, gets minus out of initial percentage of his life.
- Player.gotskilled: Player, who got killed in the game, receives a message to wait 3 minutes out of game.
- Player.recharge: If player’s charge amount becomes zero, he or she gets a message to recharge device. Recharging happens by shaking a device.
- Map.track: Points represent players on map.
- Map.radar: On tracking map, detector of distance to or from a treasure, will change its color. 
- Bonus.get: On tracking map, player can see bonuses and get them.
- Bonus.hide: Activates bonus in a way of hiding a player’s point on tracking map in radius of 10 meters.
- Bonus.undead: Activates bonus in way of letting get a life in case of getting killed in the game.
- Bonus.use: Checks, whether player already used bonus in a process of the game. If was, rejection message will appear.
- Bonus.ask: Ordinary player sends request to commander, asking the possibility of using a bonus.
- Treasure.get: When player is in distance of 1 meter from a treasure, he gets it.
- Victory.yes: Winner team gets victory screen.
- Victory.no: Loser team gets screen with a message that they have lost the game.



*Non-functional system requirements*   


**Usability:**

Since several actions are taken by players themselves in advance such as dividing into teams and choosing a commander, also in the game there is no specific need to have a unique username, the time of procedure to start a game is short. Start screen is well designed and it is easy to use for user of all ages.

In case of any failure, the informative error messages will appear for user, leading to help facilities to actions user should take. 

The application strongly based on visual appearance and well-formed graphics to guide user throughout a game process.

**Reliability:**


The application is responsive and designed for specific requirements of running device. Ability of the application to perform the functions for given time of a game is convenient. Rate of application’s failure is low. 


**Efficiency:**

The advantage of our system is that the amount of people that are going to use it at the time is limited by the game’s rule, excluding the overload problem of the system and guarantying the speed. 

The games process is combination of a devices and our software. Customers are expected to be experienced in using smartphones as well as different application. Meaning that they could easily get involved in game by using the application running on device. Graphics on the screen help to understand to player what is going on the map, also visual messages are going to support all needed information.


*Other non-functional requirements:*

**Flexibility** – software is configurable if it has the ability to handle a wide variety of system configuration sizes. On the other hand, flexibility is applied when the software intends to increase or extend the functionality after its deployment.

**Dependability** – the application is highly depends on hardware and the Internet connection.

**Scalability** – the ability of smartphone and the application to change in size to meet a user need should function well.


Metrics guarantee unambiguity:
- The system is available for service when requested by user
- Reputation from technical and social points of view of customers
- Excellent syncing of the application and device
- Performance: speed and response of the application


5. User interface
=======


*Main components of user interface:*

* Life indicator 

Location: Bottom left corner
Description: Life rate decreasing when you got shot, also you can see the percentage rate that represents how many life resources player has left

Indicator of bullets left 

Location: Top left corner
Description: There are 10 load 10 bullets in each. By syncing app understands when player shoot. When player ran out of bullets systems gives screen notification that you need to recharge your weapon by shaking it. 

* Timer 

Location: Top right corner
Description: Shows how many time until the end of the game (in total 20 mins)

* Temperature treasure radar 

Location: Bottom left corner beside life indicator
Description: Temperature radar changes color when player comes closer to the treasure (blue-further than 30 meters; light purple-further that 20 meters; pink – further than 10 meters; red – treasure in 10 meters radius)

* Bonuses

Location: Bottom right corner 
Description: There are two bonuses in the game: Undead and Hide. Team can use each bonus only once in the game. So when player trying to activate the bonus by touching representative icons, the commander going to decide approve or decline bonus usage.

![myflowcart](http://users.metropolia.fi/~anastab/software_p/IMG_7491.JPG)

![myflowcart](http://users.metropolia.fi/~anastab/software_p/IMG_7492.JPG)



6. Project management, self-reflection
==========
 
Resource allocation:

* Time: 5-6 weeks
* Human resources: 3 software programmers,1 graphical designer, 1 project manager
* Money: no information about finances 


Project scheduling 

1.Beginning (1 week)   

* Clear documentation
* Main functions
* Primary graphical design
* Meeting with customer every 1,5 week



2.Implementation (3 weeks)
 
* Working code
* Error handling 
* Adapting graphics
* Test syncing with weapon device
* Meeting with customer
* Update documentation


3.Finishing up (1-2 weeks)

* Testing all functions
* Final meeting with 
* Working graphical interface
* Testing user interface and usability of app
* Update documentation

     

*Self-assessment*

* Disscussion of the idea for a project : 3 hour 
* Mock-up creation : 4 hours 
* Documentation : 8 hours
* Overall working hours : 15 ; 7.5 per each member

From the begging of this project, we have decided that customer related documentation such as user cases and user interface would be done by one member and more technical side like functional requirements by another. It can be said, that previous experience in the past courses helped a lot. And also, we have already long-term relationship working as a team therefore it was easy to divide tasks and workload. Actual workload took approximately the same amount as was expected. The only issue is was find the time for this exact project among the other pending at the same period.
The idea of application is clever and bright. From a functional side, it difficult to say whether application is perfect, because of lack of knowledge in software development. On the other hand, this application is unique and entertaining.
The difficult part in documentation was describe system and its functional requirements, because we do not yet have experince in application development. But, we did some research on game's system architecture.





	 














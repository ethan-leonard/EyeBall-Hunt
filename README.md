#Eye Ball Hunt
#### Video Demo: https://youtu.be/55kdGFo7oqA

#### Images:
![image](https://github.com/user-attachments/assets/b640b393-fdb9-4215-81ab-42a9d7697945)
![image](https://github.com/user-attachments/assets/3262808b-4b94-485b-b4b0-4651c4b7ed15)
![image](https://github.com/user-attachments/assets/99dc4433-5827-4551-a94d-7dd32c60af70)
![Uploading image.png…]()


#### Description:
For my CS50 final project, I first begun my making a list of all the possible ideas I had for things I could create. After a couple days of brainstroming, I finally decided that I wanted to make a game for my final project. This is where I encountered my first challenge, I had no idea games were made. Thanks to CS50 though, I knew that I would be able to pick up new skills much faster then before, so I set out to locate a course that could teach me everything I needed to know about video game design. Pior to CS50, the only game engine I had heard of was Unity, so that is where I decided to start. I was able to locate a course called Create With Code which is made by Unity, and after looking at some reviews, I decided this is what I would be going with. Then for the next couple weeks, I worked my way through the 40 hour course, absorbing as much information as possible.

After I was fairly knowledgable in C# and the Unity game engine, I set out to draft ideas for the project. I wanted to intialy make a golf game, similar to Game Pigeon golf, but I soon discovered that the creation of the aiming and movement system for that type of game would require dozens of more hours of researching due to it not being covered the Create with Code course. Knowing this, I decided to make a game that instead ultized all the knowledge I gained from the course to avoid spending even more time, I was feeling a bit burnt out. This is when I decided to create a game similar to the likes of Fruit Ninja, as I was extremely confident that I would be able to pull it off.

Gameplay: In my game, there are four different objects, three "good" objects and one "bad" object. The goal of the game is to click on the good objects as they fly into the game screen while avoiding the bad objects. Each good object gives the player a set number of points which is stored and displayed in the score varible in the top left of the screen. The beach ball is worth five points, the eightball is ten points and the eyeball is worth fifteen points. Clicking on the bomb will result in the lose of fifty points. The game ends when one of the good game objects falls below the screen or when the score is below zero. There are three game modes, easy, medium, and hard. The user can select a game mode on the title screen via buttons that also begin the game. Each game mode increases difficulty by increasing the spawn rate of the game objects.

This game also features animations that make it so upion clicking on the game objects, a particle explosion will apear shooting out from the object.

In Target.cs, under the start function, the game objects are shot into the are and forced to rotate by using the AddForce and AddTorque functions. The OnMouseDown function detects when the mouse is clicked down. If the game is running and a game object is clicked, the object is destroyed, a particle explosion is spawned in at that point and the score variable is updated. The OnTriggerEnter function destroys the game objects when they fall down and collide with the collider, and then compares the tag of the game object to see if it is a good game object. If it is, the game is set to game over. RandomForce function returns a Vector3 that is a random number from the selected range. The RandomSpawnPos also returns a Vector3 that is a random number from the selected range. It is used to determine the spawn position of the game objects.

In DifficultyButton.cs, under the start function, there is an event listener that detects when the difficulty buttons are clicked. The SetDifficulty function then logs in the console which button was clicked and the game is started with the selected difficulty.

In GameManager.cs, under the update function, there is a function that detects if the score drops below zero, and if it does, game over is activated. The SpawnTarget function is responsible for the timing of the spawn of objects. When the game is active, it waits a certain amount of time deteremined by the SpawnRate variable and when that time is elasped, it selects a random game object from a list to spawn. The UpdateScore function ensures that the score is displayed accurately on the screen when the game is started. The GameOver function ends the game by triggering the game over text and the restart button to appear on the screen and setting the game to not active which prevents game objects from spawning. The StartGame function takes an int for difficulty and sets the game status to active. It then calculates the spawnRate by using the difficulty variable and truggers the spawn target function. It then sets the score to 0, removes the title screen text and activates the score text.

Overall, this project was a ton of fun today. I am excited to begin something new, wether it is starting a new couse, or working on another game!


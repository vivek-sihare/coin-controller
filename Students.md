🍯 Coin Collector — Step-by-Step (Year 4)

- Goal: Move your player, collect coins, avoid the enemy.
- Get points, keep lives, and beat the 30-second timer.

### Before you start

- Open a web browser and go to https://arcade.makecode.com/
- Click New Project → name it Coin Collector → choose Blocks view.

### STEP 1 — Welcome message

- Where: Game
- Drag show long text into the workspace.
- Click the text and type:
- Coin Collector!!
- Set layout to CENTER.
- This message will show at the start.

### STEP 2 — Create the player

- Where: Sprites.
- Drag set mySprite to sprite of kind Player.
- Click the small image and draw a player (simple square or smiley).
- Rename the block variable to player (click the variable name).
- Drag set mySprite position to x y (Sprites) and set x = 80, y = 60.
- From Controller, drag move mySprite with buttons vx vy, choose player and set vx = 100, vy = 100 (or vy = 0 if you want only left/right).

### STEP 3 — Score, lives and timer

- Where: Info
- Drag set score to 0.
- Drag set life to 3.
- Drag start countdown (s) and type 30.
- These blocks set the score, give 3 lives and start a 30 second game.

### STEP 4 — Spawn coins every 1 second

- Where: Game / Sprites
- From Game drag on game update every 1000 ms (1000 ms = 1 second).
- Inside it, from Sprites, drag set mySprite to sprite of kind Player and change to create sprite of kind Food (use the create sprite block and pick kind Food).
- Draw a small coin picture.
- After creating coin, set position: set sprite x to random 10 to 150 and set sprite y to random 10 to 110 (or set y = 0 to drop from top).
- (Optional) Set velocity so the coin moves: set sprite vy to 50.
- Add set sprite auto destroy to on so coins disappear if off screen.

### STEP 5 — Spawn enemy every 1.5–3 seconds

- Where: Game / Sprites
- From Game drag on game update every 3000 ms (3 seconds).
- Inside, create a new sprite of kind Enemy (use create sprite of kind Enemy).
- Draw the enemy (e.g., a red square).
- Set enemy position to random X and Y: x = pick random 10 to 150, y = pick random 10 to 110.
- Set velocity: set enemy vx to 50 and set enemy vy to 50.
- Turn bounce on wall ON for the enemy: set enemy bounce on wall to true.
- Set auto destroy on so it cleans up.

### STEP 6 — When player collects a coin (score + sound)

- Where: Sprites, Music, Info
- From Sprites drag on sprite of kind Player overlaps otherSprite of kind Food.
- Inside:
- change score by 1 (Info)
- destroy otherSprite with effect confetti (Sprites → choose confetti)
- play sound ba ding (Music)
- This runs every time the player touches a coin.

### STEP 7 — When player hits the enemy (lose life + reset position)

- Where: Sprites, Info, Game, Music, Logic
- From Sprites drag on sprite of kind Player overlaps otherSprite of kind Enemy.
- Inside:
- change life by -1 (Info)
- play sound wawawawaa (Music)
- pause 500 ms (Game)
- Use an if block (Logic): if life > 0 then:
- show string or show long text → "Try again! Lives left: " + life (use the join text block to join text and number)
- set player position x 80 y 60
- else:
- game over lose with effect melt (Game)
- This reduces lives and either restarts position or ends the game.

### STEP 8 — When time runs out (win)

- Where: Info / Game
- From Info drag on countdown end.
- Inside:
- game over win with effect confetti (Game)
- This gives a win when the 30 seconds finish.

### STEP 9 — Reset the game with button B

- Where: Controller, Info, Game, Sprites
- From Controller drag on button B pressed.
- Inside:
- set life to 3
- set score to 0
- start countdown 30
- set player position to x 80 y 60
- game splash "Game Reset! Try again!"
- This lets students restart quickly.

### STEP 10 — Test & Play

- Click Play in the simulator.
- Move the player using the arrow keys or controller.
- Try to collect coins and avoid the enemy.
- Watch the score, lives and timer at the top.

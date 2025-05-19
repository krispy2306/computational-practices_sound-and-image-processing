# Week 9 Tasks
- Explored vectors and motion 
- Explored basics of object-oriented programming


**Requirements:**

- Written in Processing 4.4.4
- Run files in Processing
- Ensure 'ball' and 'player' class files are also downloaded for 
the game sketch to work



**GAME Weekly Task:**

Aim: Make a game using:
- at least 1 class
- at least 2 forces influencing the object movement
- at least 1 type of interaction


Decided to develop from class code - 'bouncing ball'


Brainstorming ideas for game:
- 2 forces acting on the bouncing balls - gravity and wind
- Aim of the game is to avoid the balls
- Add player - a square shape?

- kept base code from class the same but changed the circles' radius to 5 so they were bigger for the player to avoid
- began implementing a Player class
- needed to create keyboard input for player movement:
```void update() {
    //check for keys
    if(LEFT) {
      vx = -5;
    }
    else if(RIGHT) {
      vx = 5;
    }
    if(UP){
      vy = -5;
    }
    if(DOWN){
      vy = 5;
    }
    // update position
    x += vx;
    y += vy;
```
- player properties:

```void display() {
    stroke(255, 255, 255);
    strokeWeight(4);
    fill(255, 0, 0);
    rect(x, y, w, h);
```

```Player() {
    x = width/ 2;
    y = width / 2;
    w = 30;
    h = 30;
    vx = 0;
    vy = 0;
  }
```

- Realised 4 balls is a bit too much for the player to dodge, so changed the number to 3 
- Horizontal movement was working but vertical wasn't - forgot to update vy values so separated code into vertical and horizontal counterparts:

'''//horizontal movement
    if(LEFT) {
      vx = -5;
    }
    else if(RIGHT) {
      vx = 5;
    }
    else if(!LEFT && !RIGHT) {
      vx = 0;
    }
    
    // vertical movement
    if(UP) {
      vy = -5;
    }
    else if(DOWN) {
      vy = 5;
    }
    else if(!UP && !DOWN) {
      vy = 0;
    }
'''

- Now just needed to add collisions - if the 'Player' square hits a circle, the game will reset (call setup()?)
- Collisions function: 

'''void collisions() {
      for (Ball b : balls) {
      float px = p.x;
      float py = p.y;
      float pw = p.w;
      float ph = p.h;
      
      float bx = b.position.x;
      float by = b.position.y;
      float br = b.radius;
      
      float closestX = constrain(bx, px, px + pw);
      float closestY = constrain(by, py, py + ph);
      
      float distanceX = bx - closestX;
      float distanceY = by - closestY;
      
      float distanceSquared = distanceX * distanceX + distanceY * distanceY;
      
      if(distanceSquared < br * br) {
        setup();
      }
    }
  }
'''

- But collisions aren't really working well - problems with detecting edges 
- deleted closestX + Y and distanceX + Y values and replaced with:
'''if(bx + br > px && bx - br < px + pw &&
       by + br > py && by - br < py + ph) {
      setup();
      '''

- collisions work slightly better, but size of the balls is too big - reduced radius to 2 


FINAL NOTE: Collisions don't really work perfectly - sometimes it will not detect when the player is colliding wit a circle
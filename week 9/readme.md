# Week 9 Tasks
- Explored vectors and motion 
- Explored basics of object-oriented programming


**Requirements:**

- Written in Processing 4.4
- Run files in Processing
- Ensure 'ball' and 'player' class files are also downloaded for 
the game sketch to work

**Game_2 Weekly Task**

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
'''  void update() {
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
'''
- player properties:
'''  void display() {
    stroke(255, 255, 255);
    strokeWeight(4);
    fill(255, 0, 0);
    rect(x, y, w, h);'''
'''  Player() {
    x = width/ 2;
    y = width / 2;
    w = 30;
    h = 30;
    vx = 0;
    vy = 0;
  }'''
  
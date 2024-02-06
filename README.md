# Klondike-2023
Klondike Project for OOD

                                   Klondike - CS3500
                                    By Kevin Jones

Overview:
Klondike is the most popular version of Solitare in the world. This project allows a user to play one of three types of Klondike games:
1. Basic
2. Whitehead
3. Limited Draw

This project emphisizes the separation of the MVC design process and focuses heavily on model design, and less so on the actual front end.
For this project, all we were given was the KlondikeModel interface, and the rest was designed by me.

Quickstart:
A user may use the main method, entering in one of:

  "basic"
  
  "whitehead"
  
  "limited" followed by an integer stating how many redraw attempts the user wants
  
Optionally followed by one or two integers which may specify the number of piles (set to seven by default), and the number of visible draw cards.

The game is then played on the command line which shows the updated board after each move is played.

Keys to play:

basic: 
        the traditional version of klondike with the goal of moving all cards up to the foundation piles. Moving cards must alternate in color, 
        and the cards that have not yet been on bottom of a pile are face down.
        
limited:
        the same rules as whitehead, but the number of draw attempts is limited to the number initiated when the game began.
        
whitehead:
        similar rules to traditional klondike with three main exceptions
            1. no color alternation: red on red, black on black
            2. same suit movement. Not only do cards need to be the same color, but to move across piles, they must also be the same suit.
            3. all cards delt face up.
            
Move inputs:
  
  mpp int1 int2 int3:
    moves int2 number of cards from pile number int1 to pile number int3. (one based counting sysytem)
    
  md int:
    moves the topmost draw card to the given cascade pile
    
  mpf int1 int2:
    moves the bottommost card in the int1 pile to foundation pile int2
    
  mdf int:
    moves the topmost draw card to the given foundation pile
    
  dd:
    discards the topmost draw card to the bottom of the deck
    
    
    
Key Skills:

  Abstracting
    A large portion of this project was centered around abstracting code where it made sense. The largest portion of this came through abstracting
    commonality amongst the three gametypes and overriding their differences. Another large portion of abstracting in this project came through
    testing as I wrote a single abstract testing class which tested all models of the KlondikeModel interface on their interface level implementations
    and then allowed for simple testing to be added on in the lower classes.
  MVC
    This was our first look at the Model-View-Controller design pattern which allowed us to think through interface segregation and information hiding.
    Privatizing fields, writiing readable javadoc, and defending my design choices were also large parts of learning this design pattern.
    

Key components:

     TraditionalKlondikeModel which is the abstract class implementing the KlondikeModel. This class sets the standardard ruleset for Klondike which
     can be extended and overridden to implement rulechanges.
     
     KlondikeTextualController which is the way the user putting inputs into the command line is able to interact with the view and model.
     
     KlondikeTextualView which is the view printed to the command line to represent the board.

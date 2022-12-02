# Snake-Game
This is the snake game which I made from python programming using turtle method 
I will give a detail explanation for the code and how it work 



First We will be importing modules into the program and giving default values for the game
        
        
        
        
        
        
        
        
        
        import turtle
         import time
         import random
              delay = 0.1
               score = 0
               high_score = 0
               
               
               
               
               
               
               
               
Secondly We will create a window screen for the game where we will create the head of the snake and food for the snake in the game and displaying the scores at the header of the game

# Creating a window screen
wn = turtle.Screen()
wn.title("Snake Game")
wn.bgcolor("blue")

# the width and height can be put as user's choice
wn.setup(width=600, height=600)
wn.tracer(0)


# head of the snake
head = turtle.Turtle()
head.shape("square")
head.color("white")
head.penup()
head.goto(0, 0)
head.direction = "Stop"


# food in the game
food = turtle.Turtle()
colors = random.choice(['red', 'green', 'black'])
shapes = random.choice(['square', 'triangle', 'circle'])
food.speed(0)
food.shape(shapes)
food.color(colors)
food.penup()
food.goto(0, 100)


pen = turtle.Turtle()
pen.speed(0)
pen.shape("square")
pen.color("white")
pen.penup()
pen.hideturtle()
pen.goto(0, 250)
pen.write("Score : 0 High Score : 0", align="center",
		font=("candara", 24, "bold"))





Thridly,we will be validating the key for the snake’s movements. By clicking the keywords normally used for gaming ‘w’, ‘a’, ‘s’ and ‘d’, we can operate the snake’s movements around the screen.


# assigning key directions
def group():
	if head.direction != "down":
		head.direction = "up"


def godown():
	if head.direction != "up":
		head.direction = "down"


def goleft():
	if head.direction != "right":
		head.direction = "left"


def goright():
	if head.direction != "left":
		head.direction = "right"


def move():
	if head.direction == "up":
		y = head.ycor()
		head.sety(y+20)
	if head.direction == "down":
		y = head.ycor()
		head.sety(y-20)
	if head.direction == "left":
		x = head.xcor()
		head.setx(x-20)
	if head.direction == "right":
		x = head.xcor()
		head.setx(x+20)


wn.listen()
wn.onkeypress(group, "w")
wn.onkeypress(godown, "s")
wn.onkeypress(goleft, "a")
wn.onkeypress(goright, "d")














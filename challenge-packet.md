# Mars Mission Challenge Packet

#### Prerequisites and Difficulty Level

To understand and complete this challenge, you should have a basic understanding of computer programming principles in Python, including how to use variables, lists, loops, conditionals, and print statements. You will also need to know how to use the command line so that you can open, save, and manage files.

#### Introduction and Summary - Why We Use Object Oriented Principles and Libraries

In this challenge, we are making a basic version of the game Lunar Lander while learning how to use outside code in the form of libraries, and how to use object oriented programming. Libraries can be especially useful when you are trying to write something quickly and there is a known way of solving a basic part of your problem. Libraries are collections of modules and contain different functions and methods that you can use for a specific purpose. We are using the graphics library Tkinter to visually model the trajectory of your rocket. You will learn more about it below, but it is important to know that in order to use it, you must use the principles of object oriented programming.

Object oriented programming is a way of organizing code in which different virtual “objects” are created. An object can be any part of a program, from abstract concepts like an equation, to physical objects like a spaceship. Object oriented programming is useful when creating a lot of these objects, like maybe you want a whole fleet of spaceships! Some classes of objects can be imported from libraries such as Tkinter, but you can also create your own.

#### Challenge and Story

Your challenge is to build a spaceship and land it on Mars, using object-oriented programming and the Tkinter library. NASA has chosen you to be the first animal to ever do this, but it has proven to be more difficult than you think. You decide to practice using Python, so that you can understand the necessary speed to land your spaceship safely.

#### Tkinter - Library

We will use Tkinter to draw the scene for our game. Tkinter is a library, so it contains many functions that allow us to draw whatever we want. The documentation, or list of functions and how to use them, is available here. For this project, we are using the canvas widget, which is the drawing and editing widget. You will mainly use the functions under “Canvas Items”, which draw specified shapes and text. The link to this section of the documentation is here.

To understand what the language on this documentation means, let’s look at the `create_oval` function. In the documentation below, we can see the name of the function, and that it requires 1 argument, bbox. If we look below we can see that these are the coordinates of the ellipse, so if we wanted it near the center of a 400x400 square, we would type `create_oval(100, 100, 300, 300)`. The other options are not required, but let’s imagine that we also want it to be red outlined in blue. To do this, we look below and see that the colors are supposed to be strings (text). We would then write `create_oval(200, 200, fill=“red”, outline=“blue”)`. We need to also write the type of the parameters that we are using and an equal sign to tell the computer which option we are using when.

(Taken from [http://effbot.org/tkinterbook/canvas.htm])
`create_oval(bbox, \**options)`
Draws an ellipse on the canvas
_bbox_
Coordinates of the top left and bottom right corner of the ellipse, in the format `x1, y1, x2, y2`. Stands for "bounding box."
_**options_
Ellipse options.
_fill=_
Fill color. An empty string (`""`) means transparent.
_outline=_
Outline color. Default is “black”.

#### Tkinter - Object Oriented Programming

In object oriented programming, each “type” of object is called a class. It has fields—variables specific to each individual object, like position, color, or speed, and methods—functions that represent actions that the object can perform, like move or display. In order to call the method of a specific instance of a class, we need to write it like `instance.[FUNCTION]([ARGUMENTS])`.

The constructor is a special method that is automatically called when you create a new instance of a function. It often takes arguments for the instance’s fields. But where do these classes come from? You can create new classes yourself, like this:
~~~~
class Spaceship:
	def __init__(self, distance):
			self.distance = str(distance)
		def move(self):
			print(“The spaceship flew ”+self.distance+“ light years”)
~~~~

If we have a Spaceship class with the field “distance” we can create a new spaceship and save it in a variable, like this:
`ship = Spaceship(“4904”)`

Now that we have our spaceship we can call some of its methods: `ship.move()`
This will print: `The spaceship flew 4904 light years`

Other classes can be found in libraries such as Tkinter. Now is a good time to, if you haven’t already, look at the sample code to learn how to use the different classes and methods in Tkinter.

Your first challenge is to make a one-dimensional version of the game where the rocket can only move up and down. The rocket class will need two fields, the altitude and vertical speed. The idea is for vertical speed to be constantly increasing due to gravity, but the player can press a key to use the spaceship’s rocket boosters and slow down. It will also need methods to display, move, and use the rockets to accelerate (and of course a constructor).

One more tool you will need is detecting key presses. The Tk root window can detect when a key is pressed using the “bind” method:
```
root = Tkinter.Tk()
def move_spaceship(event):
    ship.move()		
root.bind('<Up>', accelerate)
```

This means that the up arrow key will be bound to the `move_spaceship` function. This function takes “event” as an argument, and in this case the event will be the pressing of the up arrow. Whenever the arrow key is pressed, the root will call move_spaceship, which will in turn call the move function of the ship object.

Once you have working one dimensional motion, you can work on adding in the second dimension by allowing the user to move the spaceship left and right by pressing the arrows.

# Other challenges
Landing Function - Once you hit the ground, gravity no longer brings you down, and you can’t fly up as easily anymore! Create a function that allows you to stay at the bottom of the screen once you get there.
Martian Storm - The weather on Mars is windier than expected, causing your spaceship to be blown to the left at the rate of one pixel per frame. How would you account for this in your simulation?
Mission Control - Create a dashboard for your spaceship that displays your position and velocity. Check out the Canvas create_text method.
Asteroid Belt - You accidentally overshoot your flight path and find yourself in the asteroid belt! Create a new asteroid class, with asteroids flying across the screen. Use inheritance to pass the x and y position of the spaceship to the asteroid so that you can have a function that checks for collisions within the asteroid class. Look here if you need some help with inheritance.

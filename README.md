# 2D Fluid Simulator
a 2D fluid simulator done entirely in python.

# start your simulation
To run the application you need to insert a valid [configuration file](#Configuration-File), and the command is the following:
```
python .\fluid.py .\config.json
```
- fluid.py: is the program's name
- config.json: is the input file where the objects of the simulation are specified
The output of the file is a gif where you can see the animation of the simulation

#### The previous command produces this gif:

![example](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/qwerty.gif)

**Note: Keep in mind that if your config file is in another folder you need to add the path accordingly**

*Example:*
```
python .\fluid.py .\configurations\config1.json
```
# Configuration File

I chose to use JSON files as inputs, because it makes it a lot easier to introduce the necessary data and because it is easy to understand.

[JSON examples](http://www2.hawaii.edu/~takebaya/cent110/json/json.html)

```
{
  "densities" : [
    {
      "pos1" : [20,25],
      "pos2" : [40,35],
      "value" : 1500.0
    }
  ],
  "velocities" : [
    {
      "pos" : [15,10],
      "direction" : [-1,1,"rxy"]
    },
    {
      "pos" : [45,50],
      "direction" : [1,1,"rxy"]
    },
    {
      "pos" : [29,29],
      "direction" : [1,-1,"rxy"]
    }
  ],
  "colors" :
    {
      "cmap" : "bone",
      "quiver" : "y"
    }	
}
```
- Densities: receives the *beginning* and *end* position of the rectangle as well as the *value* of the density we are simulating.
- Velocities: receives the *position* and *direction* of the velocity that we want to simulate.
  - direction can contain the behaviour of the force in the last element of the list if there is no specifier the force will act normally (linear).
    - rx: rotation in x axis
    - ry: rotation in y axis
    - rxy: rotation in both
-Colors: specifies the [color map](https://matplotlib.org/stable/tutorials/colors/colormaps.html) and [quiver](https://matplotlib.org/stable/tutorials/colors/colors.html) color of the plot.

And that should be everything you need to know to start playing around.

any comment or inconvience you can send me an email, to check what's wrong.

have fun!

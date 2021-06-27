# 2D Fluid Simulator
a 2D fluid simulator done entirely in python.

# start your simulation
To run the application you need to insert a valid [configuration file](#Configuration-File), and the command is the following:
```
python .\fluid.py .\config.json
```
- fluid.py: is the program's name
- config.json is the input file where the objects of the simulation are specified
The output of the file is a gif where you can see the animation of the simulation

#### The previous command produces this gif:

![example](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/qwerty.gif)

**Note: Keep in mind that if your config file is in another folder you need to add the path accordingly**

*Example:*
```
python .\fluid.py .\configurations\config1.json
```
# Configuration File

# Development Log 2D Fluid Simulator

### Starting the project

We were given a fully functional fluid simulator, so we were tasked to modify it in orderto introduce the starting conditions (densities, velocities and even colors) but first I en-counter a problem I was not expecting, it was that the animation wasn't saving properly.
Apparently I needed to have FFmpeg so I went and installed it, long story short it didn't work and I didn't know why so I tried switching the writer to Pillow and it worked like a charm, so I was finally able to start.

#### first animation created
![blooper1](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/1.gif)

### Changing Colors

With the animation finally working properly I looked for ways to change the colors of the plot elements, in my first attempt I used the function *style.use()* from the [CN color section](https://matplotlib.org/stable/tutorials/colors/colors.html) in the matplotlib documentation, the style I wanted to use is the *seaborn* style, needless to say my attempt failed.

#### seaborn style not applying
![blooper2](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/2.gif)

After sometime checking some more documentation I found that you can choose a premade [colormap](https://matplotlib.org/stable/tutorials/colors/colormaps.html) for your plot which is exactly what I needed, most of the examples will have the **hot** colormap because it is the one I liked the most.

#### hot cmap working properly

![blooper3](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/3.gif)

### Playing with the configurations

I noticed that the density was getting pulled by the velocity wich I thought was odd, so I made some different configurations to see if it happened in them as well.

#### removed the force at the left to see if the density was getting pulled by the other force

![blooper4](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/4.gif)

#### removed all forces to see if it stayed still

![blooper5](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/5.gif)

### Adding different behaviours to velocity

After understanding how the velocity works I wanted to make a more interesting scenario where the velocity is not only straight line so I tried to add rotating velocities, utilizing the cos and sin function of numpy, in my first attempt I was assigning the value directly and the result was the following.

![blooper6](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/6.gif)

As you can see it the behaviour is not what I wanted, and it was confusing because I was using the functions correctly, so I remembered something similar happened in a previous project, originally I was assigning the values directly in the update function so I modified it a bit and created the *velocity_behaviour* which does the calculations and then returns the value, and that made the trick.

### Rotations working properly in x

![blooper7](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/7.gif)

### Rotations working properly in y

![blooper8](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/8.gif)

### Two rotations 

![blooper9](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/tests/9.gif)

And that was all the problems I encountered, setting up the configurations files was an easy task thanks to the JSON format, which is very friendly for human readers and also really easy to parse in python.

### A circular rotation simulation I really liked

![blooper9](https://github.com/sodes-proxy/2D-Fluid-Simulator/blob/main/configurations/config2.gif)


## References

- http://www2.hawaii.edu/~takebaya/cent110/json/json.html
- https://matplotlib.org/stable/tutorials/colors/colors.html
- https://matplotlib.org/stable/tutorials/colors/colormaps.html
- https://stackoverflow.com/questions/40026718/different-colours-for-arrows-in-quiver-plot
- https://stackoverflow.com/questions/13316397/matplotlib-animation-no-moviewriters-available
- https://stackoverflow.com/questions/60033397/moviewriter-ffmpeg-unavailable-trying-to-use-class-matplotlib-animation-pillo

Thank you for reading!!

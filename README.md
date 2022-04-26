# Spyder-SolarData-GICC
As a part of my intern at UNAM. We build a little script to get solar flares data from National Oceanic and Atmospheric Administration (NOAA).

# Authors
- José Vidal Cardona Rosas - ladivcr@comunidad.unam.mx

# Type of licence
GNU General Public License v3.0

# How can I start the code and test on my local computer?

Clone or donwload this repository. 
The first step is:
0. **Create your enviroment**
- It's highly recommended and a good practice, create and work over a virtual enviroment. 
> You can create one using the tutorial on this [link](https://docs.python.org/es/3/tutorial/venv.html)

1. **Install MySQL on your computer**
- You need to have installed MySQL on your local computer to make your own tests
> You can use this [tutorial](https://www.solvetic.com/tutoriales/article/5373-como-instalar-mysql-8-0-en-ubuntu-18-04/)

2. **Create a new DB and one table**
- When you already installed MySQL you need to create a new database. 
> The necessary commands are on the createdDB.txt file

3. **Create a new user and give them privileges**
> You can do that with this [tutorial](https://www.digitalocean.com/community/tutorials/crear-un-nuevo-usuario-y-otorgarle-permisos-en-mysql-es)

4. Take the file **env.txt** and change to **.env**
- You need to do this because the code use _dotenv library_.

> If you're on Linux system, you can do: ```mv env.txt .env```
 
5. **Fill out the file .env**
- when you already do that, you need to **fill out the file .env** with the new user information, the port, the db name, etc

6. **Install the dependences**

- You need to use the requirementes.txt file 
> If you don't have idea how to install dependences using a requirements.txt file, don't worry it's really easy.

> Just type:
 
> ```pip3 install -r requirements.txt```


5. **That's it**
- To run the script, just type: 
> `python3 spyder.py`

# One note about the code

Inside the code, the library **solar** from pysolar needs LAT & LOW to get **altitude and azimuth**
these coordinates were got from apply some operations and corresponds to the center (aproximate) of mexico


![mexican contient with some points to split](/img/geo-coordinates.png "Points to split mexico")

If we extrapolate these points with their respective coordinates we will have

![figure that represent mexican contient with some points and their coordinates](/img/geo-coordinates-fig.png "Points with their respective coordinates")

as we can see, we have three figures. Let's take the triangle

```math
We have these points:

- D = (28.913853, -105.620773)
- E = (32.534079, -117.123331) 
- F = (22.881472, -109.962889)

If we solved these operations:
X* = (Dx + Ex + Fx)/3
X* = [28.913853 + 32.534079 + 22.881472]/3
X* = 28.1088

Y* = (Dy + Ey + Fy)/3 
Y* = [(-105.620773) + (-117.123331) + (-109.962889)]/3
Y* = -110.902331
```

Now if we take the squares and apply the equation: ```math S* = [Cx + Dx + Fx + Gx]/4```
we will have these results:
```math
Xs1* = 24.0342
Ys1* = -105.1610806

Xs2* = 20.029646
Ys2* = -96.00450633
```

Then, we take these three results and get the mean again. And we have LAT & LOW that we use inside the code. 
```math
X = [28.1088+24.0342 + 20.029646]/3 = 24.05754867
Y = [-110.902331 - 105.1610806 - 96.00450633]/3 = -104.0226393 
```

This is the justify behind these variables. 

# Spyder-SolarData-GICC
As a part of my intern at UNAM. We build a little script to get solar flares data from National Oceanic and Atmospheric Administration (NOAA).

# How can I start the code and test on my local computer?

Clone or donwload this repository. 
The first step is:
0. **Create your enviroment**
> It's highly recommended and a good practice, create and work over a virtual enviroment. 

> You can create one using the tutorial on this [link](https://docs.python.org/es/3/tutorial/venv.html)
2. **Install MySQL on your computer**
> You can use this [tutorial](https://www.solvetic.com/tutoriales/article/5373-como-instalar-mysql-8-0-en-ubuntu-18-04/)
When you already installed MySQL you need to create a new database. 

1.1. **The commands to create a DB and the table are on the createdDB.txt file**

2. **Create a new user and give them privileges**
> You can do that with this [tutorial](https://www.digitalocean.com/community/tutorials/crear-un-nuevo-usuario-y-otorgarle-permisos-en-mysql-es)

3. Take the file **env.txt** and change to **.env**
> You need to do this because the code use _dotenv library_.

> If you're on Linux system, you can do:

> ```mv env.txt .env```
 
> when you already do that, you need to **fill out the file .env** with the new user information, the port, the db name, etc

4. **Install the dependences**

> You need to use the requirementes.txt file 

> If you don't have idea how to install dependences using a requirements.txt file, don't worry it's really easy.
> Just type:
 
> ```pip3 install -r requirements.txt```


5. **That's it**
> To run the script, just type: 

> `python3 spyder.py`

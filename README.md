# COSASS (Valencia hub)
Valencia hub for the Coordinated Intelligent Services for Adaptive Smart Areas (COSASS) national project.

## Official COSASS website
The official website is located in this [link](https://cosass.usal.es).


## Software developed
### Agri-RO5
The satellital map tool is located at [Agri-RO5](https://github.com/FranEnguix/Agri-RO5) repository.

### FIVE server
FIVE is available by:

`
https://github.com/Unity-Technologies/ROS-TCP-Connector.git?path=/com.unity.robotics.ros-tcp-connector
`

`
https://github.com/Unity-Technologies/ROS-TCP-Connector.git?path=/com.unity.robotics.visualizations
`

`
https://github.com/Unity-Technologies/URDF-Importer.git?path=/com.unity.robotics.urdf-importer#v0.5.2
`

To install these packages you need to open Window > Package Manager, click the + icon and select Add Package from git URL. Then, you have to copy and paste the URLs described above, one by one.

You can click the play button to start the simulation and you can also compile your own version of the FIVE server.

## Usage
We can define the agents of our simulation, the IVE features and the objects placed in it. In order to archive this purpose we have to tweak the configuration files:


### FIVE server
You have to configure **map.txt**, **map_config.json** and **map.json** files.
- **map.txt** lets you design an environment map by writing ASCII characters.
- **map_config.json** is used to create a link between the characters of the **map.txt** and the object of the environment. For example, you may want to create a forest with a certain distribution of trees, so you can write a 'T' character in **map.txt** and then create a link with the Unity object (prefab) in **map_config.json**.
- **map.json** it is used to instantiate highly customized individual objects and light conditions. For example, you can define an empty object and name it "Agent spawner" and assign a position to it; then, you can reference this empty object by its name in **configuration.json** file and set it as the starting point of the agents. 

### FIVE client
Agents only require one configuration file, which is named **configuration.json**. This file has two sections:
- **fiveserver** is used to specify the fiveserver name and domain at the XMPP server, so agents can communicate with it.
- **agents** is a list of agents to set the agent name, avatar, starting position, etc. 

We can define the agent behaviour by creating a new Python file and setting the name of the file without the *py* extension on the **behaviour** property.

### Run FIVE

To run the IVE with the inhabitant agents you have to:
1. Run the XMPP server.
2. Run the FIVE server (Unity).
3. Run the agents by executing the **launcher.py** file.

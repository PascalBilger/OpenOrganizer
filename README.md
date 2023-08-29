# OpenOrganizer
## An automated open source storeage system for small mechanical and electronic parts

Storeage of mechanical and electronic parts always is a challenge. This is where the OpenOrganizer will hopefully come into play. It can store tens of thousands of different parts per cubic metre of space which makes it an extremely compact solution.

The goals of this project are as follows:
* OpenSource
* Reliable
* Easy and cheap to build
* Scalable
* Easy to use UI to manage the contents of the storeage

A working prototype was already built using containers wich have a size of 60 by 60mm. To see it in action visit https://www.youtube.com/watch?v=Lr_ZOjyPq00. This prototype is not reliable enough which is why there will be a next verison in which the Containers are stacked vertically instead of horizontally.

The containers are stored in a storeage made from MDF. The Boards around the storeage have a thickness of 18mm and the ones in the middle one of 5mm. The entire storeage has a size of 71.5cm in height and 97cm in width.

### Original prototype
<img src="https://github.com/PascalBilger/OpenOrganizer/blob/assets/Pictures/Interlocking_containers_example.jpg" alt="alt text" height="500" >
The original prototype relied on interlocking containers which where then moved using a gantry similar to a 3D printer. In fact the mainboard which controls it is a Ramps 1.4 which is made for 3D printers.

#### Identification
To identify the conatiners to automatically detect which container was put into the system a 2D Barcode is used. This system will be used in the new system as well but the barcode will be put on the bottom of the containers.

#### Software
The main software runs on the PC besides the storeage.
Microsoft Access was used to create a database of all containers and their contents. The Access database then exectuted a python script as soon as the desired container was selected.
The software quickly grew out of its shoes making it hard to read and unintuitive. For that reason the software will be completely redone in the new version.

#### Mechanics
The mecahnics are extremely similar to a 3D printer. The vertical movement is acieved through the use of lead screws and the movement from side to side is achieved through a GT2-Belt. One of the problems of the current mechanics is that it cant reach the bottom two rows of the storeage and is significantly bigger than the storeage itself which makes the useable space smaller than it could be. The mechanics are quite flimsy because many of the mechanical parts are 3D-printed and somewhat poorly designed.

### New version
The biggest change will be the fact that the containers will be stacked vertically instead of horizontally. That way the slow movement in Z direction due to the lead screws can be avoided using a CoreXY gantry.

#### Software
To decouple the storeage itself from the PC controlling it a raspberry Pi or similar singleboard computer will be used. The mechanics will be controlled using klipper, a remote 3D Printing software.
The database will run on the raspberry pi itself so the storeage can be controlled from every device. As a UI a server of some type will run on the raspberry pi which can be accessed from the local network.
The software to control the storeage will probably be written in python again but more attention will be paid to readability.

#### Mechanics
As mentioned the movement in X/Y direction will be accomplished using a CoreXY gantry. Instead of the interlocking containers every container will be on its own. The prototype of the mechanism to pick the containers up can be seen in this video: https://youtu.be/mREgzeUiP4E
The CoreCY gantry will move a 60 * 60mm large rectangular tube around from wich the gripper from the video will be lowered into the storeage and one container will be retreived. To move it around it will be completely pulled out of the storeage and into the moving piece until it is lowered into its destination. Using this system hopefully makes it possible to have simple yet reliable mechanics.


2025-08-14 16:17

Status:

Tags: [[ideas]] [[TO DO]] [[Project Ideas]] [[augmented reality]]  





# View object in augmented reality

>- capture images of a physical environment surrounding the device using image capture system
>- construct a map of the physical environment while simultaneously tracking and updating a location and pose of the device in the physical environment using the images captured by the image capture system and input from an inertial measurement unit in the device(Indoor positioning system)
>- register one or more markers indicating a physical location of an object fixed in the physical environment
>- display a visual graphical representation of the virtual object in the virtual marker
>- operating a physics utility in the memory to apply laws of physics to define an interaction between the virtual object and the real object

# Indoor Positioning System

>- [[smartphone sensors useful for indoor positioning]] 


# Current approaches

## Approach 1: Using 3-D recreation

>- We first map out the 3-d space and objects surrounding the position where we wish to place the virtual object
>- Then we place a virtual marker(Spatial anchor ) and recreate the mapping of the virtual object at the place where we want our virtual object on the generated 3-d space
>- To generate the 3-d mapping we have a few viable ways:
>	- The most common method we could use is "Simultaneous Localization and Mapping(SLAM)". It is the method where a device or robot constructs a map of its surroundings while simultaneously tracking its own location within that map.
>- we can rely on SLAM to compute the positioning and the pose of the device relative to the virtual object


## Approach 2: Map out just the surface

>- Here we map out just the surface where the virtual object is to be placed (_User-Defined Marker-less AR or simple edge detection_)
>- Then, we can use the input from inertial measurement unit present in smartphones such as accelerometers and gyroscopes to compute the orientational displacement of the device from the initial point to calculate the current position and orientation away from the virtual object


## Approach 3: AI for 3-d reconstruction

>- Use something like Luma AI to map out the 3-d space
>- Then place the virtual object on the 3-D space

## Approach 4: Use Google's ARcore

>- This Google's AR application can just track motion(using gyro and accelerometer), understand environment(detect table, wall, etc..) and estimate light(Guesses how bright the room is and makes the virtual object cast realistic shadows)
>- Can use a Depth model like Midas or just the model built inside ARcore for estimating the distance between objects





# References
https://patents.google.com/patent/US12189861B2/en (Augmented reality experiences with object manipulation) --this reference has a patent --the patent is owned by a person in snap Inc(The company that created snaptube)

article where it explains that having known the specifications of your sensor(sensor's width-height, output resolution), and your focal length, without taking the zoom factor into consideration, you can calculate size of an object in meters or in pixels given one of them correspondingly. (Referenced from https://stackoverflow.com/questions/11920285/how-to-determine-the-size-of-a-physical-object-image-on-a-phones-screenthis)  
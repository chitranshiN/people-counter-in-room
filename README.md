# people-counter-in-room
We here in this project detect occupancy of the room. We deployed two sensors in the room and study the effectiveness and accuracy of the solution for presence of people in the room, number of people in the room at the moment and for the time each participant was in the room. First sensor that we use is CSI camera module for raspberry pi which uses OpenCV for counting people by using face detection. Second sensor we used is ultrasonic sensor (HC-SRO4) which detects objects within its 4-5m.

This project is aimed to provide a smart solution for efficiently managing rooms in an office complex. Internet of thing (IOT) devices are becoming popular both for sensing and actuating. One of the area that has received a great impulse from the IOT field advances in the smart building framework. Action related with energy consumption in building the user is directly or indirectly involved, whether it is switching light on/off lights, adjusting the air conditioning temperature, etc. or even if just one to know that whether the room is occupied or not so that no one accidently barge in.

software development:

The software part of this system is required to gather the information from the sensor and make sense of it, as well as store this processed information on the online cloud platform of Google Firebase. 
The software first takes the reading from the ultrasonic sensor that will be placed on the door frame (and calibrated according to the width of the door). It then decides whether a person has crossed the door frame either going inside the room or outside the room using the duration it takes for an ultrasonic wave to reach back to the sensor.  The ultrasonic sensor calculates the distance of the nearest object in front of the sensor using the time it takes for an ultrasonic wave to travel from the transmitter to the object and bounce back to the receiver on the sensor. Using the speed of the ultrasonic wave in air we can calculate the distance travelled by the wave.
If a person has crossed the door frame, the software then initializes the camera to take pictures of the room to count the number of people in the room using OpenCV module and a Face Detection algorithm. The algorithm takes multiple pictures of the room so that it can take a final stable count of number of people in a room. After the final count of the number of people in the room is done, the software uploads the new number of people in the room to firebase along with the date and time when the change in the number of occupants of the room changed. 
This way instead of uploading the data from the sensors regularly and unnecessarily wasting storage space, the data is only sent to the database when there is a change in the occupants of the room.

Hardware components:

1 Ultrasonic Sensor (HC-SR04)

2 CSI Camera Module

3 Raspberry Pi 3 Model B

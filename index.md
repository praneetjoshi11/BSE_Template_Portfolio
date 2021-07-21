# Gesture Controlled Car with Accelerometer 
Hello! My name is Praneet and at BSE this summer, I will be working on a gesture controlled car with the addition of an accelerometer/gyroscope. This car will be controlled by my arm which will be linked to an ESP 32 microcontroller that will function the L298N motor driver connected to 4 DC motors, each pertaining to a wheel.  

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Praneet Joshi | Irvington High School | Electrical and Computer Engineering | Incoming Junior

![Headstone Image](https://bluestampengineering.com/wp-content/uploads/2016/05/improve.jpg)
  
# Final Milestone
My final milestone is the increased reliability and accuracy of my robot. I ameliorated the sagging and fixed the reliability of the finger. As discussed in my second milestone, the arm sags because of weight. I put in a block of wood at the base to hold up the upper arm; this has reverberating positive effects throughout the arm. I also realized that the forearm was getting disconnected from the elbow servo’s horn because of the weight stress on the joint. Now, I make sure to constantly tighten the screws at that joint. 

[![Final Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1612573869/video_to_markdown/images/youtube--F7M7imOVGug-c05b58ac6eb4c4700831b2b3070cd403.jpg )](https://www.youtube.com/watch?v=F7M7imOVGug&feature=emb_logo "Final Milestone"){:target="_blank" rel="noopener"}

# Second Milestone

[![Praneet's Second Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1626887903/video_to_markdown/images/youtube--jH0zZHIjaTw-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=jH0zZHIjaTw "Praneet's Second Milestone"){:target="_blank" rel="noopener"}

My second milestone was soldering the MPU6050 accelerometer and connecting it with a second ESP 32 microcontroller to recieve readings based on gestures made in the x, y, and z axes. Since the accelerometer also had a 3-axis gyroscope built in it, I was able to obtain both the rotational velocity and the angle of tilt in the 3 axes. Upon getting readings in the serial monitor of the Arduino IDE, I changed the unit of "radians" to "degrees" as it was easier to find a range of values in degrees. Next, I found of a range of values that would make the car move forward and backwards (x), and also left and right (y). I plugged these values into my code to recieve readings such as: "Move Forward," "Move Left." Lastly, I was able to connect the two ESP 32 microcontrollers using the "TwoWayESP" library. 

```C++
#include<Wire.h>

double x;
double y;
double z;

// Converting to Degrees

x= RAD_TO_DEG * (atan2(-yAng, -zAng)+PI);
y= RAD_TO_DEG * (atan2(-xAng, -zAng)+PI);
z= RAD_TO_DEG * (atan2(-yAng, -xAng)+PI);

// Move Forward

if(y >=30&&y <=80) {

Serial.println("Move Forward ");
Serial.println(y);

}

// Move Backward

else if(y >=300&&y <=325) { 

Serial.println("Move Backwards ");
Serial.println(y);

}

// Move Left

else if (x >=30&&x <= 65) {

Serial.println("Move Left ");
Serial.println(x);

}

// Move Right

else if (x >270&&x<=297) {

Serial.println("Move Right ");
Serial.println(x); 
}


else {

Serial.println("Stop");
Serial.println(x);
Serial.println(y);

}

// Z Direction
Serial.print("AngleZ= ");
Serial.println(z);

Serial.println("-----------------------------------------");
delay(5000);

}

``` 

![image](https://user-images.githubusercontent.com/87200454/125982851-67813d3a-6058-4a32-bf54-c537393f99d8.png)
![image](https://user-images.githubusercontent.com/87200454/125985781-1230672c-6a50-4357-98f4-0e968eb8aed4.png)
![image](https://user-images.githubusercontent.com/87200454/125986090-47644f70-732d-4c70-8e0e-c1ea77352339.png) 


# First Milestone


[![Praneet's First Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1626887792/video_to_markdown/images/youtube--JqKNtSrtwxY-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=JqKNtSrtwxY "Praneet's First Milestone"){:target="_blank" rel="noopener"}


My first milestone was setting up and hooking up the Raspberry Pi and all the necessary components onto my tv. The heatsinks, the sd card, and the controller were all added to ensure that the Raspberry Pi was working. Instead of the Raspberry Pi Os software, I had to first download a different software called Retro Pie. With Retro Pie, I needed to download an Imager for Raspberry Pi. Raspberry Pi Imager automatically downloads a list of the latest versions of Raspbian supported by the Raspberry Pi. Raspbian is the typical Raspberry Pi Os software, the one I needed on the Raspberry Pi was Retro Pi. With the included SD card, I plugged in the SD into my computer and launched the Imager. The imager allowed me to set the Operating System to Retro Pi instead of Raspbian onto the SD card. With the OS imaged onto the SD, I plugged the SD card back into the Raspberry Pi and rebooted the system and Retro Bi booted up.





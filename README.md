# Drone Motion

![N|Solid](https://www.firstpersonview.co.uk/blog/wp-content/uploads/2015/09/Inspire-1-PRO-1-1024x569.png)

 ### 1. Abstract:
>The current methods of piloting drones are difficult and not easily accessible. The average person might have an interest in drones, but does not want to spend time going through the learning curve. This exposed a void which could be filled. We present a sensor-free, accurate, and intuitive system for hand motion controlled UAV piloting. Our method efficiently classifies hand gestures from simple video capture, translating them to drone motion. Our implementation takes advantage of the strength of deep convolutional neural networks (CNN) to achieve high accuracies. In order to eliminate discrepancies due to different people and backgrounds during classification, a simple calibration technique is used to maintain reliability. Furthermore, a Discrete Bayes Filter is used to sequentially process frames and estimate the state of the system. We hope our model will serve as a platform for people to easily and intuitively fly drones.

### 2. Team Members:
  - TriVi Tran - t1tran@ucsd.edu
  - Hakan Erol - herol@ucsd.edu
  - Joji Asako - jasako@ucsd.edu
  - Soheil Karimi - skarimik@ucsd.edu
  
### 3. Technology:
- [AR Drone 2.0 Elite Edition](https://www.parrot.com/us/drones/parrot-ardrone-20-elite-edition#parrot-ardrone-20-elite-edition)
- [PS Drone API](http://www.playsheep.de/drone/index.html)

### 4. Milestones: 
#####  Hand Gesture Detection
#
Due to Deep CNNs requiring lots of data, our team will capture many video samples of the hand gestures to create a dataset. We will then train our network to accurately classify these hand gestures using video frames. Our training results will be provided by visualizing the loss and accuracy of our network. On top of new training data, in order to maintain the highest level of accuracy of hand gesture detection, we will be using a calibration system. This system asks the user to perform the ten different gestures we have implemented in order to adjust to the specific person and background. Real time testing can then be done through a demo of our classifier, which will use both the CNN and a Discrete Bayes Filter.

##### Piloting UAV
 #
We will be using a fairly inexpensive drone for testing. The AR-Drone 2 can be controlled through a full featured API, written in and for Python, known as PS-Drone. We will connect to the drone through a laptop and control it with this API. We will test all the drone movements we are planning to implement. Then we will compare the piloting performance of the computer versus the mobile app provided by the drone’s manufacturer. Results will be provided by video.

##### Connecting the Systems
#
We are going to connect our hand gesture detection system to the PS-Drone API. These results will be presented in the form of a video or if possible an outside live demo. Furthermore, our project results will also be provided in another final video along with a report.

##### Optimizing Flight
#
We will be optimizing flight of the drone using PS-Drone API. Our goal is to make everything more fluid, natural, and enjoyable for the user. 

### 6. Extension:

#### 7. Video:
[Video]
#### 8. Final Report:





   [Video]: <https://drive.google.com/file/d/0B6ZrfwStVoaTalpZdU0tQlRYX3c/view>
   

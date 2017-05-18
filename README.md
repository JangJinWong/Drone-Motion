# Drone Motion

![N|Solid](https://www.firstpersonview.co.uk/blog/wp-content/uploads/2015/09/Inspire-1-PRO-1-1024x569.png)

 ### 1. Abstract:
>The current methods of piloting drones are difficult and not easily accessible. The average person might have an interest in drones, but does not want to spend time going through the learning curve. This exposed a void which could be filled. We present a sensor-free, accurate, and intuitive system for hand motion controlled UAV piloting. Our method efficiently classifies hand gestures from simple video capture, translating them to drone motion. Our implementation takes advantage of the strength of deep convolutional neural networks (CNN) to achieve high accuracies. In order to eliminate discrepancies due to different people and backgrounds during classification, a simple calibration technique is used to maintain reliability. Furthermore, a Discrete Bayes Filter is used to sequentially process frames and estimate the state of the system. We hope our model will serve as a platform for people to easily and intuitively fly drones.

### 2. Group Management:
  - TriVi Tran - t1tran@ucsd.edu 
  - Hakan Erol - herol@ucsd.edu
  - Joji Asako - jasako@ucsd.edu
   - Soheil Karimi - skarimik@ucsd.edu
         
In our group we don't necessarily assign exact roles to members, instead we all collaborate on each aspect of the project ensuring each and every one of us understands how everything works. Keeping the same philosophy, we mostly make decisions as a whole. There are cases however, where one member might be much more knowledgable on a certain topic and we will trust their judgment on certain decisions. Still though, the rest of the group would be consulted at first so everyone is on the same page. We meet every Monday, Wednesday, and Friday to spend a few hours looking at our progress and deciding how and what we should proceed to work on next. Outside of regular meeting hours, we stick to Slack for communication. Each week we assess our progress, taking a look at our specific goals and the big picture, ensuring we are on track. If we see that we are a little behind, we will meet on extra days of the week to get back on track. 

  

  
### 3. Technology:
- [AR Drone 2.0 Elite Edition](https://www.parrot.com/us/drones/parrot-ardrone-20-elite-edition#parrot-ardrone-20-elite-edition) - A standard affordable product made by [Parrot](https://www.parrot.com/us/#drones-fpv). We chose to use this drone because it was able to do all simple flight movements, which met our requirements for this project. 
- [PS Drone API](http://www.playsheep.de/drone/index.html) - An API written in python, specifically for the AR Drone 2.0. It allows us to control the flight movement of the drone easily and to use it along with our machine learning classifier. 
- [Convolutional Neural Network](https://en.wikipedia.org/wiki/Convolutional_neural_network) - a deep learning method or a classifier that was used to predict the flight commands. The classifier requires a learning process before it can actually predicts a command. It first needs to process the images of each hand gesture, captured by the webcam, and update the belief of each movement. Then, it will try to guess the flight commands upon a new image that it receives. This allow us to use our hand gestures and translate them to drone flight commands.
- [Discrete Bayes Filter](https://en.wikipedia.org/wiki/Recursive_Bayesian_estimation) - a mathematic algorithm that updates the belief of one movement using the movement's previous belief as a hint. This allows us to improve prediction accuracy before sending the actual command to the drone by taking into account the sequential nature of video frames. The algorithm also helps eliminate some noises from our classifier's predictions.





### 4. Milestones: 
#####  Hand Gesture Detection: 5/4/17 (completed)
#
Due to Deep CNNs requiring lots of data, our team will capture many video samples of the hand gestures to create a dataset. We will then train our network to accurately classify these hand gestures using video frames. Our training results will be provided by visualizing the loss and accuracy of our network. We plan to gather lots of data in different environments in order to keep training our CNN and increase it’s accuracy. On top of new training data, in order to maintain the highest level of accuracy of hand gesture detection, we will be using a calibration system. This system asks the user to perform the ten different gestures we have implemented in order to adjust to the specific person and background. Real time testing can then be done through a demo of our classifier, which will use both the CNN and a Discrete Bayes Filter.



###### Deliverables
- [Training Images](https://github.com/TriviTran/Drone-Motion/tree/master/Movement%20Pics) (whole team) - Prepare a set of sample images of different hand gestures to visualize the dataset. This gives the audience a sense of what the CNN is training on. 
- Graphs of Accuracy/Loss (Hakan Erol) - Visualize the performance of the CNN
- Dynamic Visualization (whole team) - In real time, we will demo the classifier’s probability distribution of our hand gestures with easy to understand graphs
- [Video of hand gesture detection and a bar graph of probability distribution of all moves](https://drive.google.com/file/d/0B6ZrfwStVoaTMVR4cHZabURON3c/view?usp=sharing): 
    * rotate right/left: rotate the camera on the drone
    * move backward/forward/left/right: move the drone
    * stop and land.

##### Piloting UAV: 5/11/17 (completed)
 #
We will be using a fairly inexpensive drone for testing. The AR-Drone 2 can be controlled through a full featured API, written in and for Python, known as PS-Drone. We will connect to the drone through a laptop and control it with this API. We will test all the drone movements we are planning to implement. Then we will compare the piloting performance of the computer versus the mobile app provided by the drone’s manufacturer.

Using the PS-Drone API, we plan to test and improve the piloting of our drone through commands sent by a computer to the drone. We will write many scripts that send a variety of commands in order to understand how the drone reacts, allowing us to optimize how and when we send these commands. The goal is to achieve accurate flight with smooth transitions between motions.

###### Deliverables
- Video Demo (Whole Team) - We will present a video demonstrating the piloting of our drone with its native app, which will then be compared to piloting using PS-Drone API  
- [Video of flying with native app](https://drive.google.com/file/d/0Bztoe_bhpw1tdl9NTFdHaThGQ28/view?usp=sharing)
- [Video of flying drone with PS-Drone API via a laptop](https://drive.google.com/file/d/0Bztoe_bhpw1tTVUtbTRMMnIxOWM/view?usp=sharing)
    * Observe how in the video displaying flight with the drone's native app, the movements are jerky and hard to control. With PS-Drone, although the drone crashed due to human error, the movements of the drone are clearly much smoother and flow together much better. The main advantage of using the PS-Drone API is the fact that the drone actually moves in the direction you tell it to, where as with the phone it is quite out of control and has a mind of it's own. This along with the much smoother flight makes it a viable solution for our system. 
    

##### Connecting the Systems: 5/18/17 (old)
#
In order to reach our end goal of actually controlling the drone with our hand gestures, we need to connect the detection system along with the PS-Drone API. We will integrate the API calls into the detection system so that the sum is as intuitive as we want it to be. Given a classified hand gesture, the appropriate command will be sent to the drone. 

###### Deliverables
- Video Demo (Whole Team) - We will present a video demonstrating how the drone flies using our connected system. We will demonstrate all of our possible movements, showing the accuracy of our system. 

###### Extend to 5/28/17 (update) 
- Since the accuracy of our model is not very high when we remove the calibration, we decided to push this task back to the end of week 8. We want to focus on improving the performance of our model and generalize it. Also, pushing this task back will not affect our project because it is a last simple step, which is integrating everything together. Hakan and Trivi will work on this once we have everything ready. 


### 5. Sprint: 

##### Generalize the model: 5/26/17 (update, currently working)
 #
The model that we are using currently needs to use a calibration system in order to maintain high accuracy. This calibration system requires the user to perform all hand gestures at the current location and let the model train on these hand gestures before using the model. This allows the model to adjust to the current setting (color of background and foreground). However, we want to spend a whole week on improving the performance of our CNN models and eventually, the model will be able to obtain a high performance without using the calibration system. Our ultimate goal is to have the model be able to recognize the hand gestures of any given person right away when they walk up to the camera. To achieve this goal, we have to gather varying training data by capturing hand gestures of many different people. We are also going to try many different methods to improve our neural network. Joji and Soheil will be responsible for this task. Hakan and Trivi will also help them out as well.

###### Deliverables
- Video demo (whole team): we will have all memebers walk up to the camera, doing different hand gestures and let the model detect each gesture. We will not calibrate the model beforehand for this task.  


##### Optimizing Flight (6/5/17)
#
To improve the fluidity and intuitiveness of piloting the drone, we will spend time tweaking certain aspects of PS-Drone API calls. We will change certain parameters such as flight speed, transitions between motions, etc. in order to make the user feel like the drone is truly connected to their hand gestures, and to make the experience as enjoyable as possible. The whole team will work on this since this is the last task of our project, we all will work on this after we finish everything (make the model become general and connect it to PS-Drone)

###### Deliverables
- Video Demo (Whole Team) - We will present a video demonstrating flight before and after optimizing the flight of the drone.

### Repository Structure
- presentations: contains all presentation powerpoints, speech practice, presentation related materials.



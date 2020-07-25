# BASIC IDEA
First, we load the XML file for detecting the presence of faces and then we retrain our network with our image on five diffrent categories. After that, we import the label_image.py program and set up everything in realtime.

# DEPENDENCIES
   tensorflow
   opencv-python
    
Brief overview of each step.

## STEP 1 - Implementation of OpenCV HAAR CASCADES

"Frontal Face Alt" Classifier is used detecting the presence of Face in the WebCam. 

Next, load this file, which can be found in the label.py program. E.g.:

    #loading the xml file
    classifier = cv2.CascadeClassifier('haarcascade_frontalface_alt.xml')

Now everything can be set with the Label.py Program. So let's move to the next Step.

## STEP 2 - ReTraining Network

We are going to create an Image classifier that identifies whether a person is sad, happy and so on and then show this text on the OpenCV Window.
This step will consist of several sub steps:

- We need to first create a directory named images. In this directory, create five or six sub directories with names like Happy, Sad, Angry, Calm and Neutral.
- Now these directories are filled with respective images downloaded them from the Internet.
- Run the "face-crop.py" program 
- After getting images, network is to be retrained. For this purpose I'm using Mobilenet Model which is quite fast and accurate. To run the training, hit the got to the parent folder and open Terminal here and type the following:

      python retrain.py --output_graph=retrained_graph.pb --output_labels=retrained_labels.txt --architecture=MobileNet_1.0_224 --image_dir=images

## STEP 3 - Towards the end

Finally, I've put everything under the "label_image.py" file from where you can get evrything.
Now run the "label.py" program by typing the following in CMD/Terminal:
      
     python label.py
     
It'll open a new window of OpenCV and then identifies your Facial Expression.
Voila, mission accomplished



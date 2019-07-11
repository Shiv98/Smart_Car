# Smart Car
A prototype of Google car which is smart enough to understand road signs and perform accordingly!

**THE PROJECT IS A RESULT OF JOINT EFFORTS OF:**

- [Dharmvir Dharmacharya](https://github.com/DDharma)
- [Yashika Mittal](https://github.com/yashika0998)
- [Shivangi Gupta](https://github.com/Shiv98)
- [Manas Sinha](https://github.com/manassinha07)
- [Abhishek Soni](https://github.com/rockstarabhii)

# Sign Detection
The project has been made by three ways:
- CNN Model
- Wireless openCV model
- Wired openCV model

# CNN Model
- Test and train data is generated through openCV and ROI(region of interest) is created, desired image is extracted and file is saved in same mode/directory as of file.([refer](https://github.com/DDharma/Smart_Car/tree/master/CNN_%26_OpenCv_Model/Builing.py))
- Then we created a 2 layered convolution neural network, with a fully connected layer and then the output layer.Then we use data   augmentation to fit data into the model, through model.fit_generater. Then we saved the model by model_json. ([refer](https://github.com/DDharma/Smart_Car/tree/master/CNN_%26_OpenCv_Model/CNN_Model.py))
- We loaded all the weights from the CNN_model file and created a dictionary of the six classes: forward, stop, left, right, slow and danger. ([refer](https://github.com/DDharma/Smart_Car/tree/master/CNN_%26_OpenCv_Model/Final_Prediction.py)).
- MQTT Server was set-up and the detected sign was sent to the node using the paho MQTT library.
- The nodeMCU code is uploded to the micro-controller and thus, the program is executed.

# OpenCV CODE FOR SIGN DETECTION
First of all, circles are detected from the background, next three zones are made inside the circle for detecting the sign. The dominant color of the zones are found and the predicted sign is returned. ([refer](https://github.com/DDharma/Smart_Car/tree/master/Sign%20Detection/sign_detection.py))

## Wireless OpenCV Model
- The MQTT server is set up. ([refer](https://github.com/DDharma/Smart_Car/tree/master/OpenCV_Wireless/mqtt.py))
- The code for sending the signal through MQTT is added to the sign detection code explained above. ([refer](https://github.com/DDharma/Smart_Car/tree/master/OpenCV_Wireless/sign_detection.py))
- The nodeMCU receives the signal sent by the server and then the micro-controller performs accordingly.

## Wired OpenCV Model
- Using server.server library, the detected sign was printed on the serial monitor on connected port.
- Then the output was read by the node and the speed of motors was thus controlled.([refer](https://github.com/DDharma/Smart_Car/tree/master/OpenCV_Wired))

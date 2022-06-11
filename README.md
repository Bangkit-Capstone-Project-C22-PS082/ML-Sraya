[![N|Solid](https://camo.githubusercontent.com/aeb4f612bd9b40d81c62fcbebd6db44a5d4344b8b962be0138817e18c9c06963/68747470733a2f2f7777772e74656e736f72666c6f772e6f72672f696d616765732f74665f6c6f676f5f686f72697a6f6e74616c2e706e67)](https://www.tensorflow.org/)

# ML-Sraya
This program will processes the user's voice and will be send the notification to authorities.

We use CNN (Convolutional Neural Network) to detect the user's voice based on "Tolong" word. we seperate the data into 3 categories, there are silent, speech, and tolong. We also use the indonesian language conversation for the speech category. 

because we use the CNN model, we need to change the waveform from audio into spectogram. The challenge that we faced is the audio has random project rate (hz) and type of audio (mono or stereo), we need to set all the audio into same project rate and audio. And also because the "tolong" word data is really hard to find in Internet, so we took it from movie or youtube even text to speech.

Modeling
- we need to import some modules from keras and some additional for exchange the type of audio from stereo into mono
- normalization the layers 
- adding Conv2D for the pooling and MaxPooling2D for take the biggest value from the pool
- adding Flatten for flattening function
- adding Dense for densely connected neural network layer
- adding Dropout to prevent the overfit

the first step is normalization the layers, then we add 3 Conv2D for the pooling the first one is 64 units, the second is 64 units as well, and last is 128 units, and the biggest value will be taken by the MaxPooling, and then we use Flatten and Dense. The last thing we remove around 20% of the layers. Thereafter, we add Dense layer same as the number of categories, in this case is 3. Then we compile using Adam optimizer and SparseCategoricalCrossentropy as the loss, we fit the model and run it with 10 epochs


From this, we hope that this app can really use full for the users especially woman users so they can prevent the harassing or any kind of threaten. So if the machine learning can detect the user's voice that screaming for getting some help, it would be a great help for the authorities to find out because it will send the user's location and also the identity 

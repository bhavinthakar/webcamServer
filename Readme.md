``` Client start ```
It is a multi-threaded webcam to weblink streaming application which means it can be simultaneously opened on multiple devices
Mainfile: webstreaming.py

webstreaming.py: This code will run in the host machine where camera is located
We have integrated motion detection inside this project
We will use flask to stream our video over the web
We will use videoStream library to capture video from webcam
We will use threading for creating sessions
We will use opencv for video reading and processing the video


We will start with intialize a lock 
We will open videostream from source 0 that is webcam
We will initialize a Flask object

We will take arguments in the main function(ipaddress and port number, frame count-optional)

We will start the thread for calculating detect_motion function and flask app
Flask app will call index function which will look for index.html file
index.html will call the video_feed function which will use the generate function 
generate will encode the frame fit for sending data to the weblink


All the motion detection code is written in motion_detection.motion_detection.singlemotiondetector.py



```Client End ```

``` Server start ```
We will use url of the streaming weblink to collect data and storing the streams into fixed sized file at the server end
Mainfile:videosplitter.py

videosplitter.py: This code will be executed at the server

We will use requests library to fetch the stream from the streaming url
Date and Time library to generate filename
OS library to get the file size

We have set file_size to 50mb. So after 50mb it will create a new file

We will read the data from weblink in chunks and storing that chunks into mp4 files

``` Server End ```
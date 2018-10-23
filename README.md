# Video Doorbell, Lab 7

*A lab report by Devon Bain*

### In This Report

1. Upload a video of your version of the camera lab to your lab Github repository
1. As usual, update your class Hub repository to add your [forked IDD-Fa18-Lab7](/FAR-Lab/IDD-Fa18-Lab7) repository.
1. Answer the questions in-line below on your README.md.

## Part A. HelloYou from the Raspberry Pi

**a. Link to a video of your HelloYou sketch running.**

[Link to video](https://youtu.be/NG86eL0Tj9E)

## Part B. Web Camera

**a. Compare `helloYou/server.js` and `IDD-Fa18-Lab7/pictureServer.js`. What elements had to be added or changed to enable the web camera? (Hint: It might be good to know that there is a UNIX command called `diff` that compares files.)**

First, `pictureServer.js` has to include the node-webcam module by adding the line `var NodeWebcam = require( "node-webcam" )`. It also has to have the webcam settings in the `opts` variable and then start the webcam using `var Webcam = NodeWebcam.create( opts );`. Finally, when it receives the message `'takePicture'` from the client, it uses the webcam to take a picture and sends the picture filename back to the client.

**b. Include a video of your working video doorbell**

[Link to video](https://youtu.be/xR2z4O14SsA)

## Part C. Make it your own

**a. Find, install, and try out a node-based library and try to incorporate into your lab. Document your successes and failures (totally okay!) for your writeup. This will help others in class figure out cool new tools and capabilities.**

My modified doorbell uses a face detection library to detect whether the photo contains a face, and if it does, it roasts (insults) the person - all in good fun, of course.

For the first part, face detection, I tried to install the `face-recognition` library but it would not install for some reason. Since there are many face detection/recognition libraries, I thought it would be faster just to try a different one. I ended up installing the `face-detectify` library which works reasonably well when the photo is well-lit and not blurry. (As the below video shows, it was unable to detect my face at first in the webcam image due to bad lighting).

For the second part, roasting the user, it turns out there is a convenient node library available [just for this purpose](https://www.npmjs.com/package/roastme). Using its `random` function, it comes up with gems such as "you look like a cross between a mutilated ape and a visible fart" and "If you really want to know about mistakes, you should ask your parents." Not the most sophisticated, but it is amusing.

For the modified code, please see the modified branch of this repository.

**b. Upload a video of your working modified project**

[Link to video](https://youtu.be/1bQQbKBaeWA)

Please note I also improved the styling of the buttons and added a loading animation while the photo is processing!

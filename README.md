# Webcam Easy JS
Latest release for Devcam(https://github.com/Ashutosh102/DEVCam_a_camera_web_app) and DevCam2.0(https://github.com/Ashutosh102/DevCam_2.0).
Issues fixed.
## This is a javascript library for accessing webcam stream and taking photos.

You can easily add it as a module to your own app.

- Streaming webcam on desktop computer or mobile
- Switch back or front cameras on mobile
- Take pictures and be able to download.


## Usage

#### 1. Include script tag in html <head>
```html
<script type="text/javascript" src="https://unpkg.com/webcam-easy/dist/webcam-easy.min.js"></script>
```
    or Import into javascript
``` js
import Webcam from 'webcam-easy';
```


#### 2. Place elements in HTML
```html
<video id="webcam" autoplay playsinline width="640" height="480"></video>
<canvas id="canvas" class="d-none"></canvas>
<audio id="snapSound" src="audio/snap.wav" preload = "auto"></audio>
```

#### 3. Call constructor in javascript
``` js
const webcamElement = document.getElementById('webcam');
const canvasElement = document.getElementById('canvas');
const snapSoundElement = document.getElementById('snapSound');
const webcam = new Webcam(webcamElement, 'user', canvasElement, snapSoundElement);
```

#### 4. Start Webcam 
``` js
webcam.start()
   .then(result =>{
      console.log("webcam started");
   })
   .catch(err => {
       console.log(err);
   });
```

#### 5. Take Photo
``` js
var picture = webcam.snap();
``` 

#### 6. Stop Webcam 
``` js
webcam.stop();
```

## Functions
- start(startStream) : start streaming webcam 
  - get permission from user
  - get all video input devices info
  - select camera based on facingMode 
  - start stream
  
  startStream is optional parameter, default value is true
      
- stop() : stop streaming webcam
  
- stream() : start streaming webcam to video element
  
- snap() : take photo from webcam
  
- flip() : change Facing mode and selected camera

## Properties

- facingMode : 'user' or 'enviroment'
- webcamList : all available camera device
- webcamCount : number of available camera device

# OCR-for-BioFlo®-CelliGen®-115-Fermentation-Control-unit
In order to constantly monitor the process parameters (such as temperature, pH, oxygen saturation and stirrer speed) during a fermentation with the Bioflo®/ Celligen® 115 Bioreactor, expensive software is normally required. Since this was not available to us, I built an automatic optical character recognition (OCR) software using a raspberryPi camera, which can automatically read and save exactly these values. 

## Setup
The camera takes a picture of the touchscreen roughly every minute and automatically reads out the values, stores them and displays them as an image on an external monitor. For this purpose, a 3D printer was used to build a holder with which the Picam can focus on the screen (https://www.thingiverse.com/thing:2842300). With the library 'pytesseract' the values could be read out automatically. 


Since the screen saver of the device started after about 10 minutes, a small servo motor had to be mounted onto the controlling unit with a 3D printed encasing (https://www.thingiverse.com/thing:3121101), which touched the screen before each recording, to avoid a black screen during the screensaver.

|Setup|
|--|
|<img src="https://github.com/basti41a/OCR-for-BioFlo-CelliGen-115-Fermentation-Control-unit/blob/main/img/Setup.jpg" width="200">|




## Results
I´m quite happy with the results. Most of the time the software detects the values correctly, only minor deviations occur. 

|Agitation|DO|Temperature|pH|
|--|--|--|--|
|<img src="https://github.com/basti41a/OCR-for-BioFlo-CelliGen-115-Fermentation-Control-unit/blob/main/img/Result_Agitation.png" width="300">|<img src="https://github.com/basti41a/OCR-for-BioFlo-CelliGen-115-Fermentation-Control-unit/blob/main/img/Result_DO.png" width="300">|<img src="https://github.com/basti41a/OCR-for-BioFlo-CelliGen-115-Fermentation-Control-unit/blob/main/img/Result_Temperature.png" width="300">|<img src="https://github.com/basti41a/OCR-for-BioFlo-CelliGen-115-Fermentation-Control-unit/blob/main/img/Result_pH.png" width="300"> |


## Future
In the future I would make the following changes:

* Improve accuracy of OCR Software
* Send values automatically to a server, where the values can be monitored live and remote
* Right now one image is taken und from that, 4 sub-images are tailored and then processed. When the camera is moved only slightly, the camera/software has to be calibrated completly by hand again. 
* I archieved good results with 'EasyOCR', but i switched to 'pytesseract' in a later version. With this, the camera should be more robust against movement
      <img src="https://github.com/basti41a/OCR-for-BioFlo-CelliGen-115-Fermentation-Control-unit/blob/main/img/Figure_1_OCR_Result_EasyOCR.png" width="500">
      


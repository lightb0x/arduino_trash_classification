# Arduino trash classification TinyML example
**SNUCSE 2020 "creative integrated design"**

TinyML Team (with LG Electronics)
* Myeonghwan Ahn
* Junseo Koo
* Jaewoo Kim
* LGE mentor Chanseok Kang

LGE lent us
* Arduino Nano 33 BLE Sense
* ArduCAM OV2640
* F/F cables to connect above two

which are necessary for project

## Description
TinyML example application for Arduino Nano 33 BLE Sense

### tested environment
* arduino nano 33 BLE Sense + ArduCAM OV2640
* macOS Big Sur (v11.1, 20C69), MBPr 13" mid 2014
* arduino IDE v1.8.13
* arduino library `Arduino_TensorFlowLite` 2.1.0-ALPHA
* arduino library `JPEGDecoder` v1.8.0
* arduino library `ArduCAM` v1.0.0

### model
MobileNet v1 25% on 96x96 RGB input

6-way classification
* cardboard
* glass
* metal
* paper
* plastic
* trash

MobileNet v1 model was trained on custom ImageNet/96x96 dataset

and transfer learning into [garythung/trashnet](https://github.com/garythung/trashnet)

### how to use
1. follow official `person detection example` [instructions](https://github.com/tensorflow/tensorflow/tree/master/tensorflow/lite/micro/examples/person_detection#running-on-arduino)
2. `git clone https://github.com/lightb0x/arduino_trash_classification.git` in directory of your taste
3. `cd arduino_trash_classification` and double click on `arduino_trash_classification_ino`

## performance
* speed : takes about `930ms` per inference (takes 260ms on Raspberry Pi Zero W)
* accuracy : correctly infer `plastic` on transparent plastic bottle


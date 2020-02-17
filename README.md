where's wally
=========

Using [Mask-RCNN](https://github.com/matterport/Mask_RCNN) to solve Where's Wally. 
Refer [alseambusher / deepwaldo ](https://github.com/alseambusher/deepwaldo)
This allowed me to practice segmentation. Thank you.

## Experiment Environment

OS : ubuntu 18.04   
CUDA / CUDNN : 10.0 / 7.6   
Tensorflow Version : 1.14 or 2.0   
GPU : Geforce RTX 2080ti   


## Data

Train data : 26 images   
Validation data : 3 images   
ground truth : json file   

## Running 

Execute waldo_config.py   
NAME = "waldo"   
    IMAGES_PER_GPU = 2   
    NUM_CLASSES = 2   
    STEPS_PER_EPOCH = 100   
    DETECTION_MIN_CONFIDENCE = 0.9   
    COCO_WEIGHTS_PATH = os.path.join("models", "mask_rcnn_coco.h5")   
    MODEL_DIR = os.path.join("models", "logs")   
    DATA_DIR = "data"   

### Training

The model I trained is in the ~/wally/models folder.   
pretrainde model name : mask_rcnn_coco.h5   

If you want to learn, type the following command    

```bash

python train.py

```

### Inference 

I used Anaconda3 envs.

```bash

python predict.py [MODEL PATH] [PATH TO IMAGE]

# for example
python predict.py /home/njh/anaconda3/envs/tf1.14/lib/python3.6/site-packages/tensorflow/wally/models/logs/waldo20200212T1130/mask_rcnn_waldo_0099.h5 /home/njh/anaconda3/envs/tf1.14/lib/python3.6/site-packages/tensorflow/wally/data/val/15.jpg 

```
 

# Find-wally-using-Mask-rcnn

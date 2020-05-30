# Boomerang-Watch Semantic Segmentation 

We did this project for a masters course project at NUS - ISS (https://www.iss.nus.edu.sg/).

here we are showing the use of Mask RCNN in a real application.

We train the Mask RCNN model to detect Boomerang and Watch , and then we use the generated 
masks to predict the new images.

BW-Boomerang Watch
Guitar is a defined but not trained class. Augment/change classes to your needs.

## 1. Installation
From the [Releases page](https://github.com/matterport/Mask_RCNN/releases) page:
1. Download `mask_rcnn_coco.h5`. Save it in the root directory of the repo (the `mask_rcnn` directory).
2. Download BW images. We used combination of Flickr, and Bing API for identifying images
3. We use VGG Image anotation tool and polygon masks to be created. Online tool: https://www.robots.ox.ac.uk/~vgg/software/via/via_demo.html
4. Put that in the path `mask_rcnn\samples\train` for train, 'mask_rcnn/samples/validate' for validate and 'mask_rcnn/samples/test' for  test.




## 2. Train the MR-CNN model with pretrained weights

Train a new model starting from pre-trained COCO weights
```
python main.py train --dataset="./mask_rcnn/samples/train" --weights=coco
```

MRCNN_Boomerang_Watch_Semantic_Trainer.py: is to import necessary library/classes/functions from MR-CNN @ https://github.com/matterport/Mask_RCNN/releases and then train the network for BW using annotated image training dataset ".\mask_rcnn\samples\train"


## Run Jupyter notebooks
MRCNN-Boomerang-Watch-Validate-Test.ipynb is used to validate, test and evaluate the trained model e.g. we had stored model at ".\mask_rcnn\samplesajay-bw\bw20200530T1137\mask_rcnn_bw_0020.h5
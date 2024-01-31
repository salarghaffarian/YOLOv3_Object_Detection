<h1 align='center' style="color:#8b008b;">  YOLOv3 Object Detection 🚀</h1?>

## <span style="color:blue;">Introduction</span>

Welcome to the **YOLOv3_Object_Detection** repository! This project focuses on implementing and training a YOLOv3 (You Only Look Once) model for object detection based on a custom dataset. YOLO is a real-time object detection system that can detect multiple objects in an image with a single forward pass through the neural network.

### YOLOv3 Overview 🕵️‍♂️

**YOLOv3**, introduced by Joseph Redmon and Ali Farhadi, builds upon the success of its predecessors by improving accuracy and speed. The model divides the input image into a grid and predicts bounding boxes and class probabilities for each grid cell. YOLOv3 uses a series of convolutional layers with skip connections, making it a powerful and efficient object detection algorithm.

#### Original Paper 📑

The YOLOv3 model is described in detail in the paper titled "*YOLOv3: An Incremental Improvement*" by Joseph Redmon and Ali Farhadi. The paper was presented at the Computer Vision and Pattern Recognition (CVPR) conference in 2018. For a deep understanding of the model architecture and training strategies, it is highly recommended to read the original paper, which can be found [here](https://arxiv.org/abs/1804.02767).

### Project Goals 🎯

This repository aims to provide a step-by-step guide on training and testing a YOLOv3 model using a custom dataset obtained from the [Open Images Dataset](https://opensource.google/projects/open-images-dataset) provided by Google. The instructions below will walk you through the entire process, from setting up the environment to training the model and evaluating its performance.

Now, let's get our hands dirty and kickstart this project!


## <span style="color:blue;">Installations</span>

Let's get our hands dirty and set up the environment for this exciting project! Follow these steps to ensure a smooth installation process.

### Prerequisites 🛠️

Before we begin, make sure you have the following installed on your system:

- Python 3.8 or later
- Pip (Python package installer)

### Step 1: Clone the Repository 📥

```bash
git clone https://github.com/salarghaffarian/YOLOv3_Object_Detection.git
cd YOLOv3_Object_Detection
```

### Step 2: Create a Virtual Environment (Optional) 🌐
Note: This project is made using the python **version=3.10**.

```bash
python -m venv .venv
source .venv/bin/activate   # On windows, use '.venv\Scripts\activate'
```
### Step 3: Install Dependencies 📦
To install the same utilized packages, use the requirements.txt file to have the same packages with the same version by running terminal command below.
```bash
pip install -r requirements.txt
```

## <span style="color:blue;">Dataset Preparation</span>
This section contains the steps required for downloading and converting the format of dataset which is suitable for YOLOv3 Object Detector Model.
The **number of classes** are considered for this project is **2** and their class ID and name is provided in the table below.
| Class ID | Objects Name   |
| --------- | -------------- |
| 0         | Balloon        |
| 1         | Airplane       | 

### Step 1: Download Dataset
Use the [OIDv4_ToolKit] (https://github.com/theAIGuysCode/OIDv4_ToolKit), a Python tool that simplifies the process of downloading images from the Open Images Dataset. However, this is a forked repository of the original [OIDv4_ToolKit](https://github.com/EscVM/OIDv4_ToolKit), the reason that the forked repository is used for this project is that it also includes another useful python code named **convert_annotations.py** which is used for converting the downloaded dataset and labels into a YOLOv3_suitable format.

Follow the instructions below to take the advantage of the repository.
#### Clone the OIDv4_ToolkKit
```bash
git clone https://github.com/theAIGuysCode/OIDv4_ToolKit.git
cd OIDv4_ToolKit
```
#### Install the required packages. (You can make a virtual environment too)
```
pip install -r requirements.txt
```

#### Download the Dataset including both images of (Airplanes and Balloons) and their labels.

- As **Training** dataset I downloaded **1000** images for each classes.
```bash
python main.py downloader --classes Balloon Airplane --type_csv train --limit 1000 --multiclasses 1
```
- As **Validation** dataset I downloaded **400** images for each classes.
```bash
python main.py downloader --classes Balloon Airplane --type_csv validation --limit 400 --multiclasses 1
```
- As **Testing** dataset I downloaded **200** images for each classes.
```bash
python main.py downloader --classes Balloon Airplane --type_csv test --limit 200 --multiclasses 1
```
Once the dataset download is completed, you will find the dataset this directory. 
```
.../OIDv4_ToolKit/OID/
``` 

#### Convert the dataset into YOLOv3 format.
Use the code below to turn the downloaded Dataset into YOLOv3 format. 

```bash
python convert_annotations.py
```








## 🌐 Deep-Learning-for-Solar-Panel-Recognition
🌍 Recognition of photovoltaic cells in aerial images with **Convolutional Neural Networks** (CNNs).
**Object detection** with YOLOv5 
**image segmentation** with Unet++


## 💽 Installation 
Create a **Python 3.8** virtual environment and run the following command:

```
conda create -n panel python=3.8 -y
```
```
conda activate panel
```
```
pip install -r requirements.txt 

```
```
pip install torch torchvision --extra-index-url https://download.pytorch.org/whl/cu113

```
## 🔍 Data sources

-----------
* ### ☀ Solar Panels Dataset
    _Multi-resolution dataset for photovoltaic panel segmentation from satellite and aerial imagery_ (https://zenodo.org/record/5171712)
 

## 💻 How to start?

------------
### OBJECT DETECTION
1. Specify the location of the data in [sp_dataset.yaml](src/models/yolo/sp_dataset.yaml).
2. Preprocess and generate annotations with [yolo_preprocess_data.py](src/features/yolo_preprocess_data.py) and [create_yolo_annotations.py](src/features/create_yolo_annotations.py) respectively.
3. Run [yolo_train.py](src/models/yolo_train.py) for training. 
4. Run [yolo_detect.py](src/models/yolo_detect.py) for inference.

### SEGMENTATION
1. Specify the structure of the data in [segmentation/datasets.py](src/models/segmentation/datasets.py)
2. The code to train and run segmentation models can be found in the [notebooks section](notebooks).

## 📡 Inference
```
# After all the above steps have been completed 

python app.py

```
## 🛠 Web App
```
# Add images to web app on local or server
# Total number of panels 
# Total area of the panels 

```

## 🧪 Models
-----------
* ### Object Detection
  * **YOLOv5-S:** 

* ### Image Segmentation
  * **Unet++:** 

## 📈 Results

![](images/Capture.PNG)
---------------

### DVC cmd

1. dvc init
2. dvc repro
3. dvc dag



## AWS-CICD-Deployment-with-Github-Actions

### 1. Login to AWS console.

### 2. Create IAM user for deployment

	#with specific access

	1. EC2 access : It is virtual machine

	2. ECR: Elastic Container registry to save your docker image in aws


	#Description: About the deployment

	1. Build docker image of the source code

	2. Push your docker image to ECR

	3. Launch Your EC2 

	4. Pull Your image from ECR in EC2

	5. Lauch your docker image in EC2

	#Policy:

	1. AmazonEC2ContainerRegistryFullAccess

	2. AmazonEC2FullAccess

	
### 3. Create ECR repo to store/save docker image
    - Save the URI: xxxx
	
### 4. Create EC2 machine (Ubuntu) 

### 5. Open EC2 and Install docker in EC2 Machine:
	
	
	#optinal

	sudo apt-get update -y

	sudo apt-get upgrade
	
	#required

	curl -fsSL https://get.docker.com -o get-docker.sh

	sudo sh get-docker.sh

	sudo usermod -aG docker ubuntu

	newgrp docker
	
## 6. Configure EC2 as self-hosted runner:
    setting>actions>runner>new self hosted runner> choose os> then run command one by one


## 7. Setup github secrets:

    AWS_ACCESS_KEY_ID=

    AWS_SECRET_ACCESS_KEY=

    AWS_REGION = us-east-1

    AWS_ECR_LOGIN_URI = demo>>  566373416292.dkr.ecr.ap-south-1.amazonaws.com

    ECR_REPOSITORY_NAME = simple-app




## AZURE-CICD-Deployment-with-Github-Actions

### Run from terminal:

docker build -t chickenapp.azurecr.io/chicken:latest .

docker login chickenapp.azurecr.io

docker push chickenapp.azurecr.io/chicken:latest


### Deployment Steps:

1. Build the Docker image of the Source Code
2. Push the Docker image to Container Registry
3. Launch the Web App Server in Azure 
4. Pull the Docker image from the container registry to Web App server and run 
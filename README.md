<p align="center"><img width="40%" src="https://github.com/jinkyukim-me/GoogleColab/blob/master/img/colab_logo.png" /></p>

## What is Google Colab?
Google Colab is a free cloud service and now it supports free GPU!

## Advantages of Google Colab
* Free GPU support.
* Google Colab allows developers to use and share Jupyter notebook among each other like Google Docs.
* upports bash commands
* All major Python libraries like TensorFlow, Scikit-learn, Matplotlib etc are pre-installed.
* uilt on top of Jupyter Notebook

## Getting started with Google Colab

### 1. Map your Google Drive
To run or import python files.

	from google.colab import drive
	drive.mount('/content/gdrive')
	
<p align="center"><img width="80%" src="https://github.com/jinkyukim-me/GoogleColab/blob/master/img/flow.jpeg" /></p>

### 2. Creating folders

	!mkdir folder-name

### 3. Install libraries
Although most of the libraries come pre-installed, 
some of the not so common ones can be installed by doing.

	!pip install torch
	
### 4. Cloning Github repository in Google Colab

	!git clone https://github.com/keras-team/keras.git
	
### 5. Changing Working Directory

	%cd new-folder
	
### 6. Running Tensorboard in Google Colab

	LOG_DIR = 'tb_logs'
	!wget https://bin.equinox.io/c/4VmDzA7iaHb/ngrok-stable-linux-amd64.zip
	!unzip ngrok-stable-linux-amd64.zip
	import os
	if not os.path.exists(LOG_DIR):
	  os.makedirs(LOG_DIR)

	get_ipython().system_raw('tensorboard --logdir {} --host 0.0.0.0 --port 6006 &'.format(LOG_DIR))

	get_ipython().system_raw('./ngrok http 6006 &')

	!curl -s http://localhost:4040/api/tunnels | python3 -c \"import sys, json; print(json.load(sys.stdin)['tunnels'][0]['public_url'])"

#### 7. Using a Free GPU Runtime
Select “Runtime,” “Change runtime type,”, set “Hardware accelerator” to GPU (the default is CPU).
<p align="center"><img width="40%" src="https://github.com/jinkyukim-me/GoogleColab/blob/master/img/setting_gpu.png" /></p>

#### 8. Downloading data from the web

	!wget url
	
#### 9. Running a python script

	!python run.py
	
#### 10. Restart Google Colab

	!kill -9 -1

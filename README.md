[![zerocodebit254](https://circleci.com/gh/zerocodebit254/udacityprojectfive.svg?style=svg)](https://app.circleci.com/pipelines/github/zerocodebit254/udacity-project-five/5/workflows/f083f0c3-c1bb-42ca-bb37-aea94fd515b2)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies


Create a virtualenv and activate it with:
	1. python3 -m venv ~/.devops
	2. source ~/.devops/bin/activate

Run the following command  to install the necessary dependencies:
	make install

For Ubuntu users, you must:
	1. install hadolintto the project directory and
	2. make sure that its added to the /usr/bin/ 
	3. To test hadolint alone, 
		run: hadolint Dockerfile
If it did not give any output, this means its working fine. 
Dockerfile is the file that has the steps to set up your image and create a container later from it.


### Running `app.py`

1. to run app.py alone:  `python app.py`
2. to run in Docker:  `./run_docker.sh`
3. to run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

 ## Minikube:
Minikube MUST be running locally and started before being able to use "kubectl" and execute its commands.
Steps to use Minikube:
	1. Download and install minikube locally according to your operating system (the scripts to be executed should be cross platform)
	2. To start minikube run 
		"minikube start"
	3. Install --kubectl-- locally 
	4. Make sure it's installed correctly by running 
		"minikube version` 
	5. Check if it works by running a command `
		"kubectl version" 
Now we're able to make predictions.
	1. Run "./run_docker.sh"
	2. Run "./make_prediction.sh"in a separate terminal tab or window after number 1. 
	3.thereafter, copy paste the output from the run_docker.sh-tab into docker_out.txt file
	4. upload docker by running "upload_docker.sh"
	5. install kubernetes and minikube locally as prescribed
	6. run "run_kubernetes.sh" to run app.py in kubernetes. this may take a while. 
	7. run "./make_prediction.sh"again ina separate tab or terminal
	8. copy paste the output from the run_kubernetes tab to a kubernetes out.txt
	9. Both text files are stored in the output_txt folder
	10. Delete the minikube cluster bu running the command "minikube delete"
	11.create a .circle.ci folder with the downloaded config.yaml file in it and build  the software on the circle ci platform.


 ##Directory files description

1- output_txt_files:files for storing the output produced by making predictions using docker and kubernetes; namely docker_out and kubernetes_out text files
2- Dockerfile: a file that describes the necessary steps to setup your docker image and create a container  
3- Makefile: A file where we describe several steps for running software specifying a tag for each step, and able to run steps in the commandline using "make <tagname>"
4- requirements.txt: It contains the needed libraries and dependencies to be able to complete the project. 
5- run_docker.sh: A shell script with running steps needed for building a docker image, listing all current containers and creating a container. 
6- run_kubernetes.sh: A shell script for setting and running a docker container using kubernetes. 
7- upload_docker.sh: A shell script for uploading a local Docker image to your Dockerhub online.


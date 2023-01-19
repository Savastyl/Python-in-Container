# Python in Container

This Dockerfile is for building an image that runs a Flask application on Ubuntu. This image is based on the official Ubuntu image from the Docker Hub.

![Alt text](Screenshot%202023-01-18%20222911.png)

## Building the Image
To build the image, navigate to the directory where the Dockerfile is located and run the following command:



```
docker build -t <image-name> .

```

## Running the Container
Once the image is built, you can run the container using the following command:

```
docker run -p 80:80 <image-name> or

docker run --name <container-name> -d -p 80:80 <image-name>

```

This will start the container and map port 80 on the host to port 80 in the container.

## What's in the Image
The image is based on the official Ubuntu image and starts with the following steps:

+ **`FROM ubuntu`** : This specifies that the image is based on the official Ubuntu image.
+ **`RUN apt-get update -y`** : This updates the package list for installed packages.
+ **`RUN apt-get install python3 -y`** : This installs python3 package on the image.
+ **`RUN apt-get install python3-pip -y`** : This installs python3 pip package on the image.
+ **`RUN pip3 install flask`** : This installs Flask library on the image.
+ **`COPY . /app`** : This copies the current directory to the /app directory in the container.
+ **`WORKDIR /app`** : This sets the working directory to /app.
+ **`CMD python3 ./welcome.py`** : This starts the flask application by running the welcome.py file.

Once the container is running, you should be able to access the application by navigating to http://localhost:80 in a web browser.





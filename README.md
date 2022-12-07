# Dockerization of FastAPI app

1).Install docker

2).Open you app folder and create a new file named Dockerfile. Write the below code

    FROM python:3.9

    WORKDIR /application-docker

    COPY requirements.txt requirements.txt

    RUN pip install -r requirements.txt

    COPY . .

    CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
    
   WORKDIR /application-docker, this will create a directory named application-docker
    
   COPY requirements.txt requirements.txt, this will copy your requirements.txt file from you application to the created folder
    
   RUN pip install -r requirements.txt, this will install all the requirements for docker
    
   COPY . ., this will copy the code from your app
  
3).Build docker images
    sudo docker build --tag CONTAINER_NAME .
    
4).See the list of available images
    sudo docker images
    
5).Run the docker image
    sudo docker run CONTAINER_NAME
    
6).Run the image in detached mode (Recommended)
    sudo docker run -d -p 8000:8000 CONTAINER_NAME
    
7).To see which container is currently running
    sudo docker ps
    
8).To stop running docker container
    sudo docker stop CONTAINER_NAME or conatiner_id
    
9).To remove unused resourses
    sudo docker container prune
    
10).Force remove docker images
    sudo docker rmi -f imageName or imageId
    
11). To remove images
    sudo docker rmi imageName or imageId

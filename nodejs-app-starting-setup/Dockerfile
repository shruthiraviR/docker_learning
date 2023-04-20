#this file is an instruction file for building the image for our application

#FROM keyword is for pulling an image (base image) on top of which our app has to be build eg: ubuntu, 
#this application is a node application and hence we are pulling the node image 
FROM node

#default working directory is root directory in the docker image - this is where all the subsequent commands in this docker file gets executed 
#we can change this by using WORKDIR keyword. this change will impact all the commands to get executed in the mentioned directory 
# docker will create this folder if it does not exist in the image
#this helps to reduce the folder traversal for each and every command execution  
WORKDIR /app

#first dot tells that all the files has to be copied to the image (host file system)
#second arg specifies that where(location/directory) these files has to be stored in the image (image file system)
#image's file system is always detached from our file system 
#below line gets executed in the set WORKDIR
COPY . .

#npm install installs all the dependencies here
RUN npm install

# this is port expose command . This has to be the last command when we build an image
# this expose is optional and can be handled in the docker run command . but adding this helps the user to identify easily on which port the app is running 
EXPOSE 80

#after installation we need to start the server... it is just a command and hence can be done via run 
#RUN node server.js 
#but why RUN is not used ? RUN command gets executed as part of the image build

# this is not executed as part of image creation 
#but as part of container start up  (docker run)
CMD ["node","server.js"]
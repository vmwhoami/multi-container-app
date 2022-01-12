FROM node:14

WORKDIR /frontend

# copy the package json file to the root of the project
# this could have been written as COPY package.json /frontend
COPY package.json .

RUN npm install
# next line copies the content of where this file is located(Dockerfile) to workdirfolder (/frontend)
COPY . .

EXPOSE 3000

 

CMD [ "npm", "start" ]

#Commands to build the image 
# -t, --tag list                Name and optionally a tag in the 'name:tag' format
#docker build -t <image_name> .    #builds the image 
#docker build -t node-app .

# Command to build an image 
# docker build -t frontend .
# docker run -p 3000:3000 -d --name frontend --rm -v /home/vmwhoami/Desktop/multi-container-app/frontend/src:/frontend/src frontend

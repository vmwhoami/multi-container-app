FROM node:14

WORKDIR /backend

# copy the package json file to the root of the project
# this could have been written as COPY package.json /backend
COPY package.json .

RUN npm install
# next line copies the content of where this file is located(Dockerfile) to workdirfolder (/backend)
COPY . .

ENV PORT 80
ENV MONGO_USERNAME=vitalie
ENV MONGO_PASSWORD=secret

EXPOSE $PORT

# The next commented line is the equivalent of adding another -v app/node_modules
# This way you would have to rebuild the image
# This is an annonimous volume
# VOLUME [ "app/node_modules" ]

CMD [ "npm", "start" ]

#Commands to build the image 
# -t, --tag list                Name and optionally a tag in the 'name:tag' format
#docker build -t <image_name> .    #builds the image 
#docker build -t node-app .

#Commands to run the image
#docker run -p 3000:80 -d --name <container_name_> --rm <image_name>
# docker run --name backend --rm -d --network=mynet -v "/backend/node_modules" backend
#Bind mount command
# docker run -p 3000:80 -d --name my_container --rm -v "/home/vmwhoami/Desktop/docker_training/:/app" modulethree


#There was a problem with the image build.
# It had no node_modules folder.
# :ro => read only
# duminica is the name of the container
# -v /app/temp -v app/node_modules are volumes we don't need to specify the path
#
# docker run -p 3000:80 -d --name duminica --rm -v "/home/vmwhoami/Desktop/docker_training:/app:ro" -v /app/temp -v app/node_modules n ode-with-start-command
# docker volume --help

#RUN MONGO with authentication
#  docker run --name mongodb -d --rm -v data:/data/db  -e MONGO_INITDB_ROOT_USERNAME=vitalie -e MONGO_INITDB_ROOT_PASSWORD=secret --network=mynet mongo
# Run backend container
#  docker run --name backend -d --rm -p 80:80 -v /home/vmwhoami/Desktop/multi-container-app/backend:/backend -v logs:/backend/logs -v /backend/node_modules --network=mynet  backend 

FROM    ubuntu

RUN apt-get update && \
    apt-get -y install curl && \
    curl -sL https://deb.nodesource.com/setup | sudo bash - && \
    apt-get -y install python build-essential nodejs

RUN npm install -g nodemon

# Provides cached layer for node_modules
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN mkdir -p /src && cp -a /tmp/node_modules /src/

WORKDIR /src
ADD . /src

EXPOSE  8080

# Run app using nodemon
CMD ["nodemon", "/src/index.js"]



#build that with: docker build -t gogo/node
#then we create a node image and we link it to the mongobd container: docker run -d --name node -p 8080 --link 6379:6379 gogo/node

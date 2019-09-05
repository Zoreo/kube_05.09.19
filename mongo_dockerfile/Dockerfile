FROM        ubuntu

RUN         apt-get update && apt-get install -y mongodb

EXPOSE      6379

ENTRYPOINT  ["bst/ngnix_3node_mongo/mongo_dockerfile/"]

#run that with: docker run -d --name mongodb -p 6379:6379 mongodb




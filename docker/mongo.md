### bobdeMBP:~ bob$ docker pull mongo
Using default tag: latest
latest: Pulling from library/mongo
d519e2592276: Pull complete 
d22d2dfcfa9c: Pull complete 
b3afe92c540b: Pull complete 
a2c1234bf134: Pull complete 
05bf57f3b398: Pull complete 
4737ab85f84c: Pull complete 
6165557c172c: Pull complete 
c2ca70046d29: Pull complete 
b80a541da2a8: Pull complete 
18edd0c32639: Pull complete 
86830e28cf71: Pull complete 
71e1d772417d: Pull complete 
Digest: sha256:88e0308671a06d4ee7da41f87944ba66355b4ee3d57d57caf92f5e1938736abd
Status: Downloaded newer image for mongo:latest
docker.io/library/mongo:latest
### bobdeMBP:~ bob$ docker images
REPOSITORY            TAG       IMAGE ID       CREATED         SIZE
mongo                 latest    ca8e14b1fda6   7 days ago      493MB
nginx                 v3        6c5d1a1b1267   15 months ago   126MB
nginx                 latest    540a289bab6c   15 months ago   126MB
ubuntu                latest    cf0f3ca922e0   15 months ago   64.2MB
eclipse/ubuntu_jdk8   latest    d1f9b3b8934e   2 years ago     749MB

端口映射
### bobdeMBP:~ bob$ docker run -itd --name mongo -p 27017:27017 mongo
2a9d1ddf7d9c49d34417f87176887ddaa44584b4d358a80f83cb959e9eea1a9e
(base) bobdeMBP:~ bob$ docker ps
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                      NAMES
2a9d1ddf7d9c   mongo     "docker-entrypoint.s…"   15 seconds ago   Up 14 seconds   0.0.0.0:27017->27017/tcp   mongo
(base) bobdeMBP:~ bob$ docker exec -it mongo
"docker exec" requires at least 2 arguments.
See 'docker exec --help'.

Usage:  docker exec [OPTIONS] CONTAINER COMMAND [ARG...]

Run a command in a running container

启动mongo
### bobdeMBP:~ bob$ docker exec -it mongo mongo
MongoDB shell version v4.4.3
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb
Implicit session: session { "id" : UUID("6a8dfff6-f0cb-4781-85d5-062f0b0d708f") }
MongoDB server version: 4.4.3
Welcome to the MongoDB shell.
For interactive help, type "help".
For more comprehensive documentation, see
	https://docs.mongodb.com/
Questions? Try the MongoDB Developer Community Forums
	https://community.mongodb.com
---
The server generated these startup warnings when booting: 
        2021-01-29T09:08:20.886+00:00: Using the XFS filesystem is strongly recommended with the WiredTiger storage engine. See http://dochub.mongodb.org/core/prodnotes-filesystem
        2021-01-29T09:08:21.332+00:00: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
---
---
        Enable MongoDB's free cloud-based monitoring service, which will then receive and display
        metrics about your deployment (disk utilization, CPU, operation statistics, etc).

        The monitoring data will be available on a MongoDB website with a unique URL accessible to you
        and anyone you share the URL with. MongoDB may use this information to make product
        improvements and to suggest MongoDB products and deployment options to you.

        To enable free monitoring, run the following command: db.enableFreeMonitoring()
        To permanently disable this reminder, run the following command: db.disableFreeMonitoring()
---
### > show dbs
admin   0.000GB
config  0.000GB
local   0.000GB
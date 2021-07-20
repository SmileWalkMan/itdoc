### bobdeMBP:~ bob$ docker pull mongo<br>
Using default tag: latest<br>
latest: Pulling from library/mongo<br>
d519e2592276: Pull complete<br>
d22d2dfcfa9c: Pull complete<br>
b3afe92c540b: Pull complete<br>
a2c1234bf134: Pull complete<br>
05bf57f3b398: Pull complete<br>
4737ab85f84c: Pull complete<br>
6165557c172c: Pull complete<br>
c2ca70046d29: Pull complete<br>
b80a541da2a8: Pull complete<br>
18edd0c32639: Pull complete<br>
86830e28cf71: Pull complete<br>
71e1d772417d: Pull complete<br>
Digest: sha256:88e0308671a06d4ee7da41f87944ba66355b4ee3d57d57caf92f5e1938736abd<br>
Status: Downloaded newer image for mongo:latest<br>
docker.io/library/mongo:latest<br>
### bobdeMBP:~ bob$ docker images<br>
REPOSITORY            TAG       IMAGE ID       CREATED         SIZE<br>
mongo                 latest    ca8e14b1fda6   7 days ago      493MB<br>
nginx                 v3        6c5d1a1b1267   15 months ago   126MB<br>
nginx                 latest    540a289bab6c   15 months ago   126MB<br>
ubuntu                latest    cf0f3ca922e0   15 months ago   64.2MB<br>
eclipse/ubuntu_jdk8   latest    d1f9b3b8934e   2 years ago     749MB<br>
<br>
端口映射<br>
### bobdeMBP:~ bob$ docker run -itd --name mongo -p 27017:27017 mongo<br>
2a9d1ddf7d9c49d34417f87176887ddaa44584b4d358a80f83cb959e9eea1a9e<br>
(base) bobdeMBP:~ bob$ docker ps<br>
CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                      NAMES<br>
2a9d1ddf7d9c   mongo     "docker-entrypoint.s…"   15 seconds ago   Up 14 seconds   0.0.0.0:27017->27017/tcp   mongo<br>
(base) bobdeMBP:~ bob$ docker exec -it mongo<br>
"docker exec" requires at least 2 arguments.<br>
See 'docker exec --help'.<br>
<br>
Usage:  docker exec [OPTIONS] CONTAINER COMMAND [ARG...]<br>
<br>
Run a command in a running container<br>
<br>
启动mongo<br>
### bobdeMBP:~ bob$ docker exec -it mongo mongo<br>
MongoDB shell version v4.4.3<br>
connecting to: mongodb://127.0.0.1:27017/?compressors=disabled&gssapiServiceName=mongodb<br>
Implicit session: session { "id" : UUID("6a8dfff6-f0cb-4781-85d5-062f0b0d708f") }<br>
MongoDB server version: 4.4.3<br>
Welcome to the MongoDB shell.<br>
For interactive help, type "help".<br>
For more comprehensive documentation, see<br>
https://docs.mongodb.com/<br>
Questions? Try the MongoDB Developer Community Forums<br>
https://community.mongodb.com<br>
---<br>
The server generated these startup warnings when booting:<br>
2021-01-29T09:08:20.886+00:00: Using the XFS filesystem is strongly recommended with the WiredTiger storage engine. See http://dochub.mongodb.org/core/prodnotes-filesystem<br>
2021-01-29T09:08:21.332+00:00: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted<br>
---<br>
---<br>
Enable MongoDB's free cloud-based monitoring service, which will then receive and display<br>
metrics about your deployment (disk utilization, CPU, operation statistics, etc).<br>
<br>
The monitoring data will be available on a MongoDB website with a unique URL accessible to you<br>
and anyone you share the URL with. MongoDB may use this information to make product<br>
improvements and to suggest MongoDB products and deployment options to you.<br>
<br>
To enable free monitoring, run the following command: db.enableFreeMonitoring()<br>
To permanently disable this reminder, run the following command: db.disableFreeMonitoring()<br>
---<br>
### > show dbs<br>
admin   0.000GB<br>
config  0.000GB<br>
local   0.000GB<br>

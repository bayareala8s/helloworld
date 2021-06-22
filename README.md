# helloworld

docker ps

docker images

docker run --publish 9001:9000  helloworld:0.0.1-SNAPSHOT

docker run --publish 9002:9000  helloworld:0.0.1-SNAPSHOT

docker run --publish 9003:9000  helloworld:0.0.1-SNAPSHOT

curl http://localhost:9001

curl http://localhost:9002

curl http://localhost:9003




docker login

docker tag helloworld:0.0.1-SNAPSHOT bayareala8s/helloworld:0.0.1-SNAPSHOT

docker push bayareala8s/helloworld:0.0.1-SNAPSHOT

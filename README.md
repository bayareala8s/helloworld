# helloworld

docker ps

docker images

docker run --publish 9001:9000  helloworld:0.0.1-SNAPSHOT

docker run --publish 9002:9000  helloworld:0.0.1-SNAPSHOT

docker run --publish 9003:9000  helloworld:0.0.1-SNAPSHOT

curl http://localhost:9001

curl http://localhost:9002

curl http://localhost:9003


# Push to Docker

docker login

docker tag helloworld:0.0.1-SNAPSHOT bayareala8s/helloworld:0.0.1-SNAPSHOT

docker push bayareala8s/helloworld:0.0.1-SNAPSHOT


# Push to AWS ECR
Retrieve an authentication token and authenticate your Docker client to your registry.
Use the AWS CLI:

aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 277374794397.dkr.ecr.us-west-1.amazonaws.com

Build your Docker image using the following command. You can skip this step if your image is already built:

docker build -t helloworld .

After the build completes, tag your image so you can push the image to this repository:

docker tag helloworld:0.0.1-SNAPSHOT 277374794397.dkr.ecr.us-west-1.amazonaws.com/helloworld:0.0.1-SNAPSHOT

Run the following command to push this image to your newly created AWS repository:

docker push 277374794397.dkr.ecr.us-west-1.amazonaws.com/helloworld:0.0.1-SNAPSHOT

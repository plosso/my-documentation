# Docker build, tag and push

gcloud auth configure-docker us-docker.pkg.dev

docker tag python-base:latest us-east1-docker.pkg.dev/engineering-artifacts-dev/docker/python-base-38:v1.0.1

docker push us-east1-docker.pkg.dev/engineering-artifacts-dev/docker/python-base-38:v1.0.1

# Docker build, use gcloud token

docker build . --build-arg GCLOUD_ACCESS_TOKEN=${GCLOUD_ACCESS_TOKEN}

docker run -d -it --mount type=bind,source=/Users/patrick.losso/workspace/python-package-overjet_labeling,target=/tmp b4cc8e95fb0d

docker exec -it 1ade776cdb52 /bin/sh

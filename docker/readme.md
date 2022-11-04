# Docker build, tag and push

gcloud auth configure-docker us-docker.pkg.dev

# Example 1
docker tag python-base:latest us-east1-docker.pkg.dev/engineering-artifacts-dev/docker/python-base-38:v1.0.1
docker push us-east1-docker.pkg.dev/engineering-artifacts-dev/docker/python-base-38:v1.0.1

# Example 2
docker tag us-central1-docker.pkg.dev/devops-poc-328820/docker/my-poetry-app:9a3cfd1 us-central1-docker.pkg.dev/devops-poc-328820/docker/my-poetry-app:v0.0.1
docker push us-central1-docker.pkg.dev/devops-poc-328820/docker/my-poetry-app:v0.0.1

# Docker build, use gcloud token

docker build . --build-arg GCLOUD_ACCESS_TOKEN=${GCLOUD_ACCESS_TOKEN}

docker run -d -it --mount type=bind,source=/Users/patrick.losso/workspace/python-package-overjet_labeling,target=/tmp b4cc8e95fb0d

docker exec -it 1ade776cdb52 /bin/sh

# Run container built for linux on apple m1 chip
docker run --platform linux/amd64 -d -p 8081:8081 -it  7ed0d6a9bd8d /bin/sh

# Rebuild an image, tag, and push to gcr
git rev-parse --short HEAD
docker build -t gcr.io/devops-poc-328820/my-poetry-app:4f46abc .
docker push gcr.io/devops-poc-328820/my-poetry-app:4f46abc
tag gcr.io/devops-poc-328820/my-poetry-app:4f46abc gcr.io/devops-poc-328820/my-poetry-app:dev-v0.0.2
docker push gcr.io/devops-poc-328820/my-poetry-app:dev-v0.0.2
 
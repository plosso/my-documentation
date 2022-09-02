# ERROR: (gcloud.builds.submit) HTTPError 404: The requested project was not found.
# Reset your current project.
gcloud config set project <project_id>

# To find your PROJECT_ID run the following command in the terminal
gcloud config get project

# From Cloud Shell run the following command to create a repository for Docker images:
gcloud artifacts repositories create container-dev-repo --repository-format=docker \
--location=us-central1 --description="Docker repository for Container Dev Workshop"


# From Cloud Shell run the following command to configure Docker to use the Google Cloud CLI to authenticate requests to Artifact Registry in the us-central1 region,
gcloud auth configure-docker us-central1-docker.pkg.dev

# Run the following command to build the container image and tag it properly to push it to your repository in the next step:
docker build -t us-central1-docker.pkg.dev/$PROJECT_ID/container-dev-repo/java-hello-world:tag1 .

# Run the following command to push the container image to the repository created previously:
docker push us-central1-docker.pkg.dev/$PROJECT_ID/container-dev-repo/java-hello-world:tag1

# To set up authentication to Docker repositories in the region us-central1, run the following command:
gcloud auth configure-docker us-central1-docker.pkg.dev

# Docker pull from gcloud
docker pull us-central1-docker.pkg.dev/cloudbuild-testing-354715/my-repository/docker:latest

# List artifact repositories
gcloud artifacts repositories list

# List docker images in repository
## gcloud artifacts docker images list \
## ${REGION}-docker.pkg.dev/${PROJECT}/${REPO} \
## --filter="package=${REGION}-docker.pkg.dev/${PROJECT}/${REPO}/${IMAGE}" \
## --sort-by="~UPDATE_TIME" \
## --limit=1 \
## --format="value(format("{0}@{1}",package,version))"
### Filters the list for a specific image
### Sorts the results descending (~) by UPDATE_TIME1
### Only takes 1 value i.e. the most recent
### Outputs the results as {package}@{version}gclou
gcloud artifacts docker images list us-central1-docker.pkg.dev/cloudbuild-testing-354715/my-repository/docker

# Creating VM

## Update the OS:
sudo apt-get update

## Install NGINX:
sudo apt-get install -y nginx

## Use gcloud to create a new virtual machine instance from the command line:
gcloud compute instances create gcelab2 --machine-type e2-medium --zone

## use SSH to connect to your instance via gcloud
gcloud compute ssh gcelab2 --zone

## gcloud command, to view the project id for your project:
gcloud config get-value project

## gcloud command to view details about the project:
gcloud compute project-info describe --project $(gcloud config get-value project)

## Create an environment variable to store your Project ID:
export PROJECT_ID=$(gcloud config get-value project)
export ZONE=$(gcloud config get-value compute/zone)
echo -e "PROJECT ID: $PROJECT_ID\nZONE: $ZONE"

## View the list of configurations in your environment:
gcloud config list

## See all properties and their settings:
gcloud config list --all

## List your components:
gcloud components list


gcloud auth list
gcloud config list project

## Set region and zone:
gcloud config set compute/region us-east1
gcloud config set compute/zone us-east1-c

## Create a GKE cluster:
gcloud container clusters create --machine-type=e2-medium --zone=us-east1-c lab-cluster

## Credentials auth to cluster
gcloud container clusters get-credentials lab-cluster

## Create new hello-server app
kubectl create deployment hello-server --image=gcr.io/google-samples/hello-app:1.0  Create Kubernetes service that expose app into external traffic:  kubectl expose deployment hello-server --type=LoadBalancer --port 8080

## Inspect with:
kubectl get service

## Delete cluster:
gcloud container clusters delete lab-cluster

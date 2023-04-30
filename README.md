# Google Cloud Computing Foundations
## Lab: GSP001
## Creating a Virtual Machine

### Task 01:

gcloud config set project 'Nome Projeto'

gcloud compute instances create gcelab --zone us-central1-b --machine-type e2-medium --tags http-server,https-server --image-project debian-cloud --image-family debian-11 

gcloud compute firewall-rules create teste --allow tcp:80 --source-ranges=0.0.0.0/0 --description "Permitir tráfego HTTP"

Obs: range 0.0.0.0/0 libera a porta para todos.

gcloud compute ssh gcelab --zone us-central1-b

sudo apt-get update
sudo apt-get install -y nginx
ps auwx | grep nginx

gcloud compute instances create gcelab2 --machine-type e2-medium --zone us-central1-b

gcloud compute instances create --help

gcloud compute ssh gcelab2 --zone us-central1-b 

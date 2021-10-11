# Devops-excercise
IN LOCAL


1.- Install docker


2.- Install docker compose


3.- Clone the repo


4.- Enter in the repo and execute sudo docker-compose up -d


5.- To make sure it works run execute in your terminal curl http://localhost:5000 the expected result is:
    
    Hello from Redis! I have been seen 2 times.

In cluster
1.- Enter in the directory configs sandbox


2.- Apply the first manifest to command: Kubectl apply -f 0_namespaces.yml


3.- Apply the manifest 1, 2 and 3 whit the namespace sandbox (it is you create to 0_namespaces). Command example: kubectl -n sandbox apply -f 1_deployment.yml

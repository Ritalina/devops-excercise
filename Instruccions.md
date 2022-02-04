### DevOps Excercise #1

## Mission

Your mission is to provide a starting point for a new Microservice that the development team is about to start.
This will be part of a complex system that runs on Kubernetes, it is cloud-agnostic, and it could be even deployed on air-gapped environments. The very first version of the code is available here:

import os
from flask import Flask
from redis import Redis
app = Flask(__name__)
redis = Redis(host=os.environ['REDIS_HOST'], port=os.environ['REDIS_PORT'])
bind_port = int(os.environ['BIND_PORT'])
@app.route('/')
def hello():
    redis.incr('hits')
    total_hits = redis.get('hits').decode()
    return f'Hello from Redis! I have been seen {total_hits} times.'
if __name__ == "__main__":
    app.run(host="0.0.0.0", debug=True, port=bind_port)



## Deliverables
Following is by no means a check-list but it can give you an idea about what we are looking for:

A Github repository for developers to start working on with the provided base code.
Developers should be able to develop locally with minimum dependencies. For example, they should be able to have a running system on their laptop without the need of installing a specific Python version.
A clear description of how to start the system and get ready to develop.
Provide the Kubernetes deployment scripts/manifest/etc to deploy either on Minikube or a possible Kubernetes cluster. Configuration options including how to manage secrets.



## Implementation
These are the recommended implementation items:

Use multistage Dockerfile.
Provide a docker-compose with all the configurations and build options.
Provide a Helm chart with all the dependencies included.
Consider the following topics: Configuration files.
Security, e.g. container’s run as user
 Memory and CPU limits. vim 1_				
Readiness and liveness probes.


## Nice to have
If you are an over-achiever, you can think of adding the following:

Continuous Integration, you can use any tool.
Option to secure Redis and change in the initial code for handling that. Monitoring strategy for this microservice.
Documentation steps about how to deploy on air-gapped environments.


## Time to complete
You have this weekend to share with us your GitHub repository URL.

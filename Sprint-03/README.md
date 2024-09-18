# Design Discussion
We have our code in git repo, the goal is to deploy this in GKE Cluster.

Q.1, How to automate the docker image builds from Dockerfile ?
`As for every code change we cannot always build the docker images manually`

Q.2, Where to store the docker image in an artifactory?
`We cannot use Dockerhub as its not suitable private organization`

After this, we'll have to write deployment/service `YAML files` for `k8s deployment`
We might also need Horizontal Pod Autoscaling, Ingress, but Deployment and Service are the basic ones that we need.

Atlast, we'll find a way to deploy the docker image stored in the artifactory to GKE


Summary of question, we need to write down is the first goal, a part of design discussion before we begin
- Automated way to `build the docker image`.

- We have to `store` the Docker image in an `artifactory`.

- We have to write a deployment/service yaml files for K8 deployment.

- We have to setup `CD` to deploy these YAML manifest files to GKE using the docker image stored in artifactory.

![image](https://github.com/user-attachments/assets/39f37f4d-6123-4040-a2a2-cac719dc9232)

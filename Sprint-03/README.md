# Design Discussion
We have our code in git repo, the goal is to deploy this in GKE Cluster.

Q.1, How to automate the docker image builds from Dockerfile ?
`As for every code change we cannot always build the docker images manually`

Q.2, Where to store the docker image in an artifactory?
`We cannot use Dockerhub as its not suitable private organization`

After this, we'll have to write deployment/service `YAML files` for `k8s deployment`
We might also need Horizontal Pod Autoscaling, Ingress, but Deployment and Service are the basic ones that we need.

Atlast, we'll find a way to deploy the docker image stored in the artifactory to GKE
<br> </br>

Summary of question, we need to write down is the first goal, a part of design discussion before we begin
- Automated way to `build the docker image`.

- We have to `store` the Docker image in an `artifactory`.

- We have to write a deployment/service yaml files for K8 deployment.

- We have to setup `CD` to deploy these YAML manifest files to GKE using the docker image stored in artifactory.

![image](https://github.com/user-attachments/assets/39f37f4d-6123-4040-a2a2-cac719dc9232)

<br> </br>

The `CI/CD` tool responsible for deploying somthing to GCP from VCS (Github repository) is called `Cloud Build`.
![image](https://github.com/user-attachments/assets/09d47434-d70f-4bcc-b50e-79b159df2491)

Cloud Build is a service that can be used for any kind of CI/CD action in GCP
One such action will be using it to build our docker image
<br></br>
When we build our docker image we can store it in GCP Artifact Registry

![image](https://github.com/user-attachments/assets/63d8abd9-9221-4d07-a068-1920f462d4a2)

We can store docker images, other files as well.
<br></br>

![image](https://github.com/user-attachments/assets/19014e38-1b78-406f-84ad-b1ca4d8c4b2b)

![image](https://github.com/user-attachments/assets/6bdcf322-abd9-4050-a690-0109d8c854ff)
<br></br>

![image](https://github.com/user-attachments/assets/7e7ea27a-88fe-4423-a16a-ad3834e29856)

We have Github and GKE,
- Build docker image using `Cloud Build` (#1)
- Store the docker image in `GCP Artifact Registry` (#1)
- Deploy the image present in `GCP Artifact registry` to `GKE` using `Cloud Build` (#2), which will be triggered based on certain action in our Github Repository(#2)
- `Cloud Build` will pull the docker image and deploy in `GKE Cluster`

![image](https://github.com/user-attachments/assets/0f45d917-2fd2-4465-b37a-6830e5f089bc)

Next, what Cloud Build is, What it can/can't do and set up a Cloud Build to push docker image


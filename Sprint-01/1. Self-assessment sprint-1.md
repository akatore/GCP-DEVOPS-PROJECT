https://github.com/kodekloudhub/gcp-devops-self-assessment

To clone the repository:
```
git clone
git@github.com:kodekloudhub/gcp-devops-self-assessment.git
```
![image](https://github.com/user-attachments/assets/1b120a26-09d5-439d-aea6-9df7a2b29866)


You can also fork the repository by accessing the repository URL and clicking folk.

How to install flask: https://flask.palletsprojects.com/en/1.1.x/installation/

How to run the application locally (need to run in the root directory of the project, the same level as project’s readme.md).

Normal mode (use the below command in Python):
```
$flask run
*Running on http://127.0.0.1:5000
```

Container mode (required Docker):

Step 1: Build
```
$docker build -t hello-py
```
Step 2: Run
```
$docker run -dt --name hello-python -p 5000:5000 hello-py​​
```
You should be able to see the below screen for both modes:image

![image](https://github.com/user-attachments/assets/5651045a-0417-4ae7-a8c0-95b9a19cc600)

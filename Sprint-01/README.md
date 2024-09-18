## Self-assessment Question 

- Create a GitHub repo and clone the repo onto the local system (your laptop)
- Make changes in  **README.md** and push this change to production
- Code a basic flask application, test it locally and push this code to the main branch

`git checkout sprint-02`

`app.py`
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, Simple Flask application'
```
`requirements.txt`
```txt
flask
```

`Dockerfile`
```Dockerfile
FROM python:3.8-slim-buster

WORKDIR /app

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY . .

CMD ["python3", "-m", "flask", "run", "--host=0.0.0.0"]
```

git checkout
```shell
docker build -t python-docker-image .
```
![image](https://github.com/user-attachments/assets/0bfdeebc-0633-4c24-aa08-f6b1c5bb0c7b)

```
git add .
git commit -m "added python application"
git push origin sprint-02
# then merge the pull request
```

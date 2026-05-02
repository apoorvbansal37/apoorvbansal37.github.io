# CI/CD Pipeline using Jenkins, GitHub & Docker Hub
---

#  Aim

To design and implement a complete CI/CD pipeline using Jenkins by integrating GitHub and Docker Hub.

---

#  Objectives

* Understand CI/CD workflow
* Automate build and deployment
* Integrate GitHub, Jenkins, and Docker Hub
* Use Webhooks for automation

---

#  Tools Used

* Jenkins
* GitHub
* Docker
* Docker Hub
* Flask

---

#  Project Structure

```
my-app/
├── app.py
├── requirements.txt
├── Dockerfile
├── Jenkinsfile
```

---

#  Step-by-Step Implementation

---

##  Step 1: Create Project in VS Code

* Created folder `my-app`
* Added files:

  * `app.py`
  * `requirements.txt`
  * `Dockerfile`
  * `Jenkinsfile`

![images for exp 7](./images/image1.png)

---

##  Step 2: Write Application Code

```python
from flask import Flask
app = Flask(__name__)

@app.route("/")
def home():
    return "CI/CD is working 🚀 - Aakriti FINAL"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=80)
```


---

##  Step 3: Create GitHub Repository

* Created repo: `my-app`
* Pushed code using Git commands

```bash
git init
git add .
git commit -m "initial commit"
git push
```

![images for exp 7](./images/image2.png)

---

## Step 4: Setup Jenkins using Docker

* Created `docker-compose.yml`
* Started Jenkins container

```bash
docker-compose up -d
```

* Accessed Jenkins at:
  `http://localhost:8080`

![images for exp 7](./images/image3.png)
![images for exp 7](./images/image4.png)
![images for exp 7](./images/image5.png)
![images for exp 7](./images/image6.png)
---

## Step 5: Configure Jenkins

### ➤ Add Credentials

* Added Docker Hub token
* ID: `dockerhub-token`
![images for exp 7](./images/image7.png)
![images for exp 7](./images/image8.png)
![images for exp 7](./images/image9.png)


### ➤ Create Pipeline Job

* Selected: **Pipeline script from SCM**
* Repo URL: `https://github.com/Aakriti2312/my-app.git`
* Script Path: `Jenkinsfile`

![images for exp 7](./images/image10.png)
![images for exp 7](./images/image11.png)

---

##  Step 6: Setup Webhook

* Added webhook in GitHub
* Payload URL:

```
https://your-ngrok-url/github-webhook/
```

* Enabled push events

![images for exp 7](./images/image12.png)
![images for exp 7](./images/image13.png)

---

##  Step 7: Execute Pipeline

* Pushed code to GitHub
* Jenkins triggered automatically

### Stages executed:

* Clone Source
* Build Docker Image
* Login to Docker Hub
* Push Image

![images for exp 7](./images/image14.png)

---

## Step 8: Verify on Docker Hub

* Image: `apoorvbansal37/myapp`
* Tag: `latest`

---

## Step 9: Run Docker Container

```bash
docker run -d -p 8081:80 aakritidhawan/myapp
```

Open:

```
http://localhost:8081
```
![images for exp 7](./images/image16.png)

---

#  Workflow Diagram

```
Developer → GitHub → Webhook → Jenkins → Docker → Docker Hub
```

---

#  Observations

* Automation reduces manual work
* Jenkins simplifies pipeline creation
* Docker ensures consistency
* Webhook enables real-time triggering

---

# Result

Successfully implemented a CI/CD pipeline where:

* Code push triggers Jenkins automatically
* Docker image is built and pushed
* Full automation achieved

---


# Conclusion

This experiment demonstrates how modern DevOps tools can automate software development and deployment efficiently.

---
# 27-01-2026

## Topic: Docker Commands & Flags - HandsOn 

### Docker Basics 

To check the docker version

```bash
docker --version
```
For system-wide info such as storage driver, cgroups, images, container.

```bash
docker info
```

---
### Image Management

To list local images 

```bash
docker images
```
- -a -> show all images (including intermediate layers) 
- -q -> only image IDs


### 1. Installing Docker using Homebrew
Homebrew was used to install Docker on macOS.

```bash
brew install docker
```

### 2. Verifying Docker Installation

After installation, Docker version was checked to confirm successful setup.

```bash
docker --version
```
Output shows that Docker was installed successfully.

### 3. Downloading Docker Desktop for Mac

Docker Desktop was downloaded for macOS using the following command:

```bash
curl -L https://desktop.docker.com/mac/main/arm64/Docker.dmg -o Docker.dmg
```
This downloads the Docker Desktop installer file.

## Screenshots

### Docker Installation
![Docker Installation](./images/docker-install.jpeg)
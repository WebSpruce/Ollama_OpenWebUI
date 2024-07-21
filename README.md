# Ollama Open WebUI

This Docker Compose file sets up a multi-container application with GPU support. The ollama service handles GPU tasks, and the openwebui service depends on ollama to function properly, using its API. The configuration includes port mappings for both services and persistent storage through Docker volumes. 🛠

## To enable GPU support in your Docker container, follow these steps :
Set the distribution variable:
```
distribution=$(. /etc/os-release;echo $ID$VERSION_ID)
```
Add the NVIDIA GPG key:
```
curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add -
```
Add the NVIDIA Docker repository:
```
curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list
```
Update the package list:
```
sudo apt-get update
```
Install the NVIDIA Docker package:
```
sudo apt-get install -y nvidia-docker2
```

Configure docker desktop settings:
- Open Docker Desktop and go to Settings:
    - Click on the gear icon in the top right corner.
- Enable WSL 2 Based Engine:
    - Navigate to the "General" section.
    - Check the box that says "Use the WSL 2 based engine".
    - Integrate with Your Default WSL Distro:
- Navigate to the "Resources" section.
    - Click on "WSL Integration".
    - Ensure your default WSL distro is selected for integration.
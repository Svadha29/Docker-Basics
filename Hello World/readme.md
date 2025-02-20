# Docker Experiment: Building a Python-Based Container 🚀
---

## 📂 **Creating the Application File**  
First, create a Python file named **`app.py`** with a simple print statement:  

```python
print("Hello, World!")
```

---

## 📖 **Documentation & Resources**  
Here are some useful references for Docker:  
🔹 [Official Docker Documentation](https://docs.docker.com/)  
🔹 [Docker Desktop Guide](https://docs.docker.com/desktop/)  

---

## 🚀 **Deployment Guide**  

Follow these steps to deploy a basic application using Docker:  

## Prerequisites
- Docker installed ([Download Here](https://www.docker.com/get-started))
- Basic knowledge of Docker commands
- A working internet connection
- Python environment (for testing `requirements.txt` separately)

## Steps to Perform the Experiment

### 1️⃣ Setting Up the Project Directory
Ensure you are inside your project folder:
```bash
cd /path/to/your/docker/project
```
Verify required files exist:
```bash
ls -l
```
Ensure `Dockerfile` and `requirements.txt` are present.

### 2️⃣ Writing the Dockerfile
Create or edit the `Dockerfile`:
```dockerfile
# Use the official Python 3-slim image as base
FROM python:3-slim

# Set the working directory
WORKDIR /app

# Copy requirements.txt into the container
COPY requirements.txt .

# Install dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the application code
COPY . .

# Command to keep the container running (modify as needed)
CMD ["python", "app.py"]
```

### 3️⃣ Creating `requirements.txt`
If missing, create a `requirements.txt` file:
```bash
touch requirements.txt
```
Edit it to include required dependencies, e.g.:
```bash
streamlit
```

### 4️⃣ Building the Docker Image
Run the following command to build the image:
```bash
docker build -t my_app .
```
If using `buildx`, run:
```bash
docker buildx build -t my_app .
```

### 6️⃣ Running the Container
Once the image builds successfully, run it:
```bash
docker run -d --name my_container my_app
```

## Conclusion
This experiment provided hands-on experience with Docker image building, dependency management, and debugging common issues. 🚀

---
_This project is a part of my Docker learning journey! ⚓_



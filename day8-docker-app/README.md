# DevOps Winter Arc — Day 08
## Docker Fundamentals

### Problem
No major issue encountered while running the Dockerized web application.

### Evidence
Used `docker ps`, `docker logs`, `docker inspect`, and `curl` to verify the container and application.

### Root Cause
N/A — the application started successfully without a port conflict.

### Fix
No fix was required. The container was started using host port 8081 mapped to container port 80.

### Verification
Verified the application using:

```bash
curl http://localhost:8081


If you **do encounter a real port conflict**, don't use the above blindly. Tell me what happened and we'll document the actual **Problem → Evidence → Root Cause → Fix → Verification**.

---

# 🧠 Before submitting, make sure you can explain these

### 1. Image vs Container

**Image** = packaged template.

**Container** = running/created instance of an image.

Example:

```text
nginx:alpine
     ↓
   Image
     ↓
docker run
     ↓
 Container

# Docker Basics Lab – Image & Container Lifecycle

This lab documents the commands from your terminal history in a structured sequence, including the purpose of each command and expected outcome.

---

# Lab Objective

By completing this lab, you will learn how to:

* Verify Docker installation
* Download Docker images
* Run containers
* Map container ports
* View logs
* Start and stop containers
* Delete containers
* Remove Docker images
* Clean up unused Docker resources

---

# Step 1: Verify Docker Installation

Check whether Docker is installed correctly.

```bash
docker --version
```

Example Output

```text
Docker version 28.x.x, build xxxxx
```

---

# Step 2: View Available Docker Images

Initially, there may not be any images available.

```bash
docker images
```

or

```bash
docker image ls
```

---

# Step 3: Download the Latest Nginx Image

Pull the latest image from Docker Hub.

```bash
docker pull nginx:latest
```

Expected Result

```
latest: Pulling from library/nginx
Downloaded newer image for nginx:latest
```

---

# Step 4: Verify Downloaded Images

```bash
docker images
```

Output

```
REPOSITORY   TAG      IMAGE ID
nginx        latest   xxxxxxxxx
```

---

# Step 5: Run an Nginx Container (Foreground Mode)

```bash
docker run nginx
```

Characteristics

* Runs in foreground
* Terminal remains attached
* Press **Ctrl+C** to stop

---

# Step 6: Run an Nginx Container in Detached Mode

```bash
docker run -d nginx
```

Options

* `-d` → Detached (background)

Docker returns the Container ID.

Example

```
d5a5f39ea797
```

---

# Step 7: View Container Logs

```bash
docker logs d5a5
```

or

```bash
docker logs <container_id>
```

Shows

* Startup logs
* Errors
* Application output

---

# Step 8: List Running Containers

```bash
docker container ls
```

or

```bash
docker ps
```

---

# Step 9: Run Nginx with Port Mapping

Expose container port **80** on host port **80**.

```bash
docker run -d -p 80:80 nginx
```

Syntax

```
HostPort:ContainerPort
```

Now access

```
http://localhost
```

---

# Step 10: Port Conflict Example

Running another container on the same host port causes an error.

```bash
docker run -d -p 80:80 nginx
```

Expected Error

```
Bind for 0.0.0.0:80 failed:
port is already allocated
```

---

# Step 11: Use a Different Host Port

```bash
docker run -d -p 1000:80 nginx
```

Access

```
http://localhost:1000
```

---

# Step 12: View Running Containers Again

```bash
docker container ls
```

Displays

* Container ID
* Image
* Status
* Ports
* Names

---

# Step 13: Pull a Specific Version of Nginx

```bash
docker pull nginx:1.31
```

If the tag exists, Docker downloads that version.

> **Note:** If `1.31` does not exist on Docker Hub, Docker returns a **manifest unknown** error.

---

# Step 14: Verify Images

```bash
docker images
```

---

# Step 15: Incorrect Command Example

Command used

```bash
docker run -d -p nginx:1.31
```

This is **incorrect syntax**.

Correct syntax

```bash
docker run -d -p 2000:80 nginx:1.31
```

Explanation

* Host Port → 2000
* Container Port → 80
* Image → nginx:1.31

Access

```
http://localhost:2000
```

---

# Step 16: List Running Containers

```bash
docker container ls
```

---

# Step 17: Stop a Running Container

```bash
docker container stop c7e41fc62709
```

or

```bash
docker stop c7e41fc62709
```

---

# Step 18: Start a Stopped Container

```bash
docker container start c7e41fc62709
```

---

# Step 19: Verify Running Containers

```bash
docker container ls
```

---

# Step 20: View All Containers

Shows both running and stopped containers.

```bash
docker ps -a
```

---

# Step 21: Remove a Container

Attempt

```bash
docker container rm c7e41fc62709
```

If the container is running, Docker returns

```
Error response from daemon:
cannot remove a running container
```

---

# Step 22: Stop Then Remove

```bash
docker container stop c7e41fc62709
```

Then

```bash
docker container rm c7e41fc62709
```

---

# Step 23: Verify Remaining Containers

```bash
docker container ls
```

---

# Step 24: View Docker Images

```bash
docker images
```

---

# Step 25: Remove an Image

Using Image ID

```bash
docker rmi b5a9a3cfc86b
```

or

```bash
docker image rm b5a9a3cfc86b
```

---

# Step 26: Force Remove Containers

Remove containers without manually stopping them.

```bash
docker container rm 4c1346ba31a0 -f
```

```bash
docker container rm bc4de0c34198 -f
```

```bash
docker container rm d5a5f39ea797 -f
```

Equivalent

```bash
docker rm -f <container_id>
```

---

# Step 27: Verify Containers

```bash
docker container ls
```

---

# Step 28: Verify Images

```bash
docker images
```

---

# Step 29: Remove Image by Name

```bash
docker rmi nginx:latest
```

or

```bash
docker image rm nginx:latest
```

---

# Step 30: Verify Images

```bash
docker images
```

---

# Step 31: Remove Another Image

Attempted

```bash
docker rmi nginx:1:31
```

This is **incorrect**.

Correct command

```bash
docker rmi nginx:1.31
```

---

# Step 32: Remove Image by ID

```bash
docker rmi b5a9a3cfc86b
```

---

# Step 33: Clean Entire Docker System

```bash
docker system prune -a
```

Removes

* Stopped containers
* Unused networks
* Dangling images
* Unused images
* Build cache

Docker asks

```
Are you sure? [y/N]
```

Type

```
y
```

---

# Step 34: View Command History

```bash
history
```

---

# Docker Command Summary

| Command                        | Purpose                        |
| ------------------------------ | ------------------------------ |
| `docker --version`             | Check Docker version           |
| `docker images`                | List images                    |
| `docker pull nginx:latest`     | Download image                 |
| `docker run nginx`             | Run foreground container       |
| `docker run -d nginx`          | Run background container       |
| `docker logs <id>`             | View logs                      |
| `docker container ls`          | Running containers             |
| `docker ps -a`                 | All containers                 |
| `docker run -d -p 80:80 nginx` | Port mapping                   |
| `docker stop <id>`             | Stop container                 |
| `docker start <id>`            | Start container                |
| `docker rm <id>`               | Remove container               |
| `docker rm -f <id>`            | Force remove container         |
| `docker rmi <image>`           | Remove image                   |
| `docker system prune -a`       | Remove unused Docker resources |
| `history`                      | View shell history             |

---

# Important Points to Remember

* Docker images are **read-only templates**.
* Containers are **running instances** of images.
* One image can create **multiple containers**.
* Use `-d` to run containers in the background.
* Port mapping syntax is always `HostPort:ContainerPort`.
* A host port can only be used by **one container** at a time.
* A running container **cannot be removed** without stopping it or using `-f`.
* Images in use by containers cannot be removed until the dependent containers are deleted.
* `docker system prune -a` is a powerful cleanup command—use it carefully in production environments.

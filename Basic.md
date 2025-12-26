---
title: Basic
updated: 2025-12-26 18:29:33Z
created: 2025-12-26 18:29:12Z
---

Docker Essentials – Clean Notes (Optimized for Joplin Markdown)
1. Docker Basics
Docker is a containerization platform used to package applications with their dependencies and run them consistently across environments.

Key Concepts
Image → Blueprint (read-only)
Container → Running instance of an image
Volume → Persistent storage
Network → Communication layer
Swarm → Docker’s native clustering / orchestration
Service → Scalable workload in Swarm
Stack → Group of services (Compose + Swarm)
2. Docker CLI – New Format (Recommended)
Docker supports a structured command format:

docker <object> <action>

Examples:

```bash
docker container run
docker network ls
docker service ps
```

Old commands still work, but the new format is clearer and interview-friendly.

---

## 3. Docker Container (Most Used)

### Run Containers

```bash
docker container run nginx
docker container run -d nginx
docker container run -it ubuntu bash
docker container run --name web nginx
```

### Useful Run Options

```text
-p 8080:80            → Port mapping
-v vol1:/data         → Volume mount
-e ENV=prod           → Environment variable
--rm                  → Auto remove container
--restart unless-stopped
--network net1        → Attach to network
--ip 172.20.0.10      → Static IP (custom bridge only)
```

### Manage Containers

```bash
docker container ls
docker container ls -a
docker container stop <id>
docker container start <id>
docker container restart <id>
docker container rm <id>
docker container logs <id>
docker container exec -it <id> sh
docker container inspect <id>
docker container stats
docker container prune
```

---

## 4. Docker Image

```bash
docker image ls
docker image pull nginx:latest
docker image build -t app:1.0 .
docker image rm nginx
docker image inspect nginx
docker image prune -a
```

---

## 5. Docker Network

Docker networks allow containers to communicate securely.

### Network Commands

```bash
docker network ls
docker network create net1
docker network inspect net1
docker network rm net1
docker network connect net1 container1
docker network disconnect net1 container1
```

### Create Network with Options

```bash
docker network create --driver bridge net1

docker network create --driver overlay net2

docker network create \
  --driver bridge \
  --subnet 172.20.0.0/16 \
  --gateway 172.20.0.1 \
  net_custom
```

### Network Drivers

- **bridge** → Single host (default)
- **overlay** → Swarm / multi-host
- **host** → No isolation
- **none** → No networking
- **macvlan** → Direct LAN access

---

## 6. Ports, EXPOSE, and Nginx Example

### Important Clarification

- `EXPOSE` only documents ports
- It does **NOT** publish ports

### Common Patterns

```text
-p 2000:80     → Host 2000 → Container 80 (recommended)
-p 2000:2000   → Works only if app listens on 2000
```

### Run Nginx on Port 2000 (Best Way)

```bash
docker container run -d -p 2000:80 nginx
```

---

## 7. Docker Volume

```bash
docker volume ls
docker volume create vol1
docker volume inspect vol1
docker volume rm vol1
docker volume prune
```

Use volume with container:

```bash
docker container run -v vol1:/data nginx
```

---

## 8. Docker Swarm (Cluster Mode)

Swarm turns Docker into a cluster manager.

### Initialize & Manage Swarm

```bash
docker swarm init
docker swarm init --advertise-addr <IP>
docker swarm join-token worker
docker swarm leave
docker swarm leave --force
```

### Nodes

```bash
docker node ls
docker node inspect <node>
docker node promote <node>
docker node demote <node>
docker node update --availability drain <node>
```

---

## 9. Docker Service (Swarm Workload)

```bash
docker service create nginx
docker service ls
docker service ps web
docker service inspect web
docker service scale web=3
docker service update --image nginx:alpine web
docker service update --force web
docker service rm web
```

---

## 10. Docker Stack (Compose + Swarm)

```bash
docker stack deploy -c docker-compose.yml app
docker stack ls
docker stack services app
docker stack ps app
docker stack rm app
```

---

## 11. Swarm Debugging & Logs (Very Important)

### First Commands to Run

```bash
docker service ps <service>
docker service logs <service>
docker node ls
```

### Service Logs

```bash
docker service logs web
docker service logs -f web
docker service logs --since 10m web
docker service logs --tail 50 web
docker service logs -t web
```

### Container Behind a Task

```bash
docker container logs <container_id>
docker container exec -it <container_id> sh
```

### Network Debugging

```bash
docker network inspect net1
ping <service_name>
cat /etc/resolv.conf
```

Swarm DNS IP:

```text
127.0.0.11
```

### Docker Engine Logs (Linux)

```bash
journalctl -u docker -f
```

---

## 12. Swarm Debug Flow (Interview Ready)

```text
docker service ps        → Why failing?
docker service logs      → What error?
docker node ls           → Where running?
docker network inspect   → Connectivity?
journalctl -u docker     → Engine issue?
```

---

## 13. Practical Recommendations

- Prefer **custom bridge networks** over default bridge
- Use `-p host:container` wisely
- Use **filesystem sync** for Dropbox when SSL issues occur
- Prefer **official DMG** for Electron apps if Homebrew causes TLS issues
- Use `docker service update --force` for safe redeploys

---

## 14. Mental Model (One Line Each)

```text
docker container run → single container
docker compose up    → multi-container app
docker swarm         → cluster mode
docker service       → scalable workload
docker stack         → production deployment
docker network       → communication & isolation
```

---
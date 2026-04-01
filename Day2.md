# Day 2: Docker Volumes

## Introduction to Docker Volumes

Docker volumes are used to persist data generated and used by Docker containers. Volumes are the preferred mechanism for persisting data because they are managed by Docker and work on both Linux and Windows containers.

### Why Use Volumes?
- Data persistence: Data is not lost when the container is removed.
- Sharing data: Volumes can be shared between multiple containers.
- Backup and restore: Volumes can be easily backed up or restored.

## Types of Docker Storage
1. **Volumes** (managed by Docker)
2. **Bind mounts** (link to a specific location on the host)
3. **tmpfs mounts** (stored in host memory, not persisted)

## Basic Volume Commands

### 1. Create a Volume
```
docker volume create my_volume
```

### 2. List Volumes
```
docker volume ls
```

### 3. Inspect a Volume
```
docker volume inspect my_volume
```

### 4. Remove a Volume
```
docker volume rm my_volume
```

## Using Volumes with Containers

### 1. Mount a Volume to a Container
```
docker run -d --name my_container -v my_volume:/data nginx
```
This mounts the `my_volume` volume to the `/data` directory inside the container.

### 2. Mount a Host Directory (Bind Mount)
```
docker run -d --name my_container -v /path/on/host:/data nginx
```

## Sharing Volumes Between Containers
```
docker run -d --name container1 -v shared_volume:/data busybox

docker run -d --name container2 --volumes-from container1 busybox
```

## Backing Up and Restoring Volumes

### Backup
```
docker run --rm -v my_volume:/data -v $(pwd):/backup busybox tar cvf /backup/backup.tar /data
```

### Restore
```
docker run --rm -v my_volume:/data -v $(pwd):/backup busybox tar xvf /backup/backup.tar -C /
```

## Cleaning Up Unused Volumes
```
docker volume prune
```

## Summary
- Volumes are the best way to persist and manage data in Docker.
- Use `docker volume` commands to create, inspect, and manage volumes.
- Volumes can be shared, backed up, and restored easily.

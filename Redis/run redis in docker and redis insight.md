# Connecting Redis to RedisInsight

This guide explains how to connect your Redis server running in a Docker container to RedisInsight, a GUI tool for managing and visualizing Redis data.

---

## Step 1: Verify Redis is Running

To ensure Redis is running properly, follow these steps:

1. **List Running Docker Containers**
   ```bash
   docker ps
   ```
   Ensure that a container with the image name `redis` is listed.

2. **Check Redis Container Logs**
   ```bash
   docker logs <container_id>
   ```
   Replace `<container_id>` with the ID or name of your Redis container.

3. **Connect to Redis CLI**
   Run the following command to enter the Redis CLI:
   ```bash
   docker exec -it <container_id> redis-cli
   ```
   Inside the Redis CLI, run the `PING` command:
   ```
   PING
   ```
   A successful response should be:
   ```
   PONG
   ```

---

## Step 2: Install RedisInsight

Download and install RedisInsight from the official Redis website:
[RedisInsight](https://redis.com/redis-enterprise/redis-insight/).

### Installation Steps:
- Download the appropriate version for your operating system.
- Install RedisInsight by following the on-screen instructions.

---

## Step 3: Add Redis Database in RedisInsight

After launching RedisInsight, follow these steps to connect it to your Redis server:

1. Click **"Add Redis Database"**.
2. Provide the following details:
   - **Host**: `127.0.0.1` (if Redis is running locally in Docker).
   - **Port**: `6379` (default Redis port).
   - If Redis requires authentication, enter the **password**.
3. Click the **"Test Connection"** button to ensure the connection works.
4. If successful, click **"Add"** or **"Connect"** to establish the connection.

---

## Step 4: Explore RedisInsight

Once connected, you can use RedisInsight's features to:
- Inspect keys and data.
- Run Redis commands.
- Monitor Redis performance.
- Visualize data structure usage.

---

## Notes

### Port Mapping for Docker
If Redis is not exposed to your host, map the container port to your local machine:
```bash
docker run -d -p 6379:6379 redis
```

### Troubleshooting
- Ensure the Redis container is running (`docker ps`).
- Verify that the port `6379` is not blocked by your firewall.
- Check Docker logs for errors (`docker logs <container_id>`).

---

## Example Command Summary

### Check Running Containers
```bash
docker ps
```

### View Redis Logs
```bash
docker logs <container_id>
```

### Access Redis CLI
```bash
docker exec -it <container_id> redis-cli
```

### Run PING Command in Redis CLI
```bash
PING
```

### Start Redis with Port Mapping
```bash
docker run -d -p 6379:6379 redis
```

---

With RedisInsight, managing Redis becomes significantly more intuitive and efficient. Happy exploring!

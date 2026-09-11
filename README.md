# uptimecuma-debian
# 1.Установка docker 
```bash
curl -fsSL https://get.docker.com -o get-docker.sh && sh get-docker.sh
```
# 2. Поднятие uptime cuma
```bash
cd /opt
mkdir uptimecuma
cd uptimecuma
```

`docker-compose.yml`
```yaml
services:
  uptime-kuma:
    image: louislam/uptime-kuma:2
    restart: unless-stopped
    volumes:
      - ./data:/app/data
    ports:
      # <Host Port>:<Container Port>
      - "3001:3001"
```
# 3. Поднимаем его
```bash
docker compose up -d
```

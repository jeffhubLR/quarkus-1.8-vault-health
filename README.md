# quarkus-1.8-vault-health

Quarkus 1.8.0.Final issue with Vault healthcheck

## Testing steps

### Start Vault

```
docker-compose up
```

### Start service to see health success with vault running

```
mvn compile quarkus:dev
curl localhost:8080/health
```

### Stop Vault

```
docker-compose down
```

### See failed health check

```
curl localhost:8080/health
```

### Start service from runner.jar

```
java -jar target/code-with-quarkus-1.0.0-SNAPSHOT-runner.jar
```
Attempt same permutations of hitting health endpoint via `curl http://localhost:8080/health` both with and without Vault running to see that this problem happens even when not in dev-mode.
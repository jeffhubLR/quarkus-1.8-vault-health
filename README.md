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

## Testing with other versions of Quarkus

Maven profiles exist for 1.4.2.Final and 1.3.4.Final. They can be used by appending `-Pquarkus-1.4.2.Final` or `-Pquarkus-1.3.4.Final` on to any `mvn` command.

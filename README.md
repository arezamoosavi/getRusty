# getRusty
Hands on small application with Rust

## Running
for running app:
```bash
docker-compose up --build -d
```
for stopping:
```bash
docker-compose down
```

## URLs

curl http://localhost:8000/health

curl http://localhost:8080/test

curl http://localhost:8080/params/1234

 curl -X POST http://localhost:8080/send -d '{"name": "alireza", "active": false }'
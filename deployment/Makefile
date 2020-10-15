set-params-ip:
	docker network inspect bridge
	code /etc/docker/daemon.json
	sudo systemctl daemon-reload
	sudo systemctl stop docker
	sudo systemctl start docker

start-registery:
	docker-compose -f docker-registery.yml up --build -d

clean-registery:
	docker-compose -f docker-registery.yml down -v

docker-build:
	docker build -t menel-api .
	docker tag menel-api 192.168.0.1:5000/menel-api:v1

docker-run:
	docker run -p 3000:80 --name menel-api -it --rm 192.168.0.1:5000/menel-api:v1

docker-push:
	docker push 192.168.0.1:5000/menel-api:v1

check-registry:
	curl -X GET http://192.168.0.1:5000/v2/menel-api/tags/list

del-minikube:
	minikube delete

init-minikube:
	minikube start --insecure-registry="192.168.0.1:5000"
	minikube ip
	minikube status

all-deploy:
	kubectl apply -f k8s/

delete-all-deploy:
	kubectl delete -f k8s/

logging:
	kubectl get all
	kubectl logs -f pod/seaside-api-784b847fc6-cvf4d
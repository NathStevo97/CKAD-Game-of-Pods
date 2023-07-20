up: namespace vote-up redis-up worker-up db-up result-up

down: result-down db-down worker-down redis-down vote-down delete-namespace

namespace:
	@kubectl apply -f ./namespace.yaml

delete-namespace:
	@kubectl delete -f ./namespace.yaml

vote-up:
	@kubectl apply -f ./vote-deployment.yaml
	@kubectl apply -f ./vote-service.yaml

vote-down:
	@kubectl delete -f ./vote-deployment.yaml
	@kubectl delete -f ./vote-service.yaml

redis-up:
	@kubectl apply -f ./redis-deployment.yaml
	@kubectl apply -f ./redis-service.yaml

redis-down:
	@kubectl delete -f ./redis-service.yaml
	@kubectl delete -f ./redis-deployment.yaml

worker-up:
	@kubectl apply -f ./worker.yaml

worker-down:
	@kubectl delete -f ./worker.yaml

db-up:
	@kubectl apply -f ./db-deployment.yaml
	@kubectl apply -f ./db-service.yaml

db-down:
	@kubectl delete -f ./db-service.yaml
	@kubectl delete -f ./db-deployment.yaml

result-up:
	@kubectl apply -f ./result-deployment.yaml
	@kubectl apply -f ./result-service.yaml

result-down:
	@kubectl delete -f ./result-service.yaml
	@kubectl delete -f ./result-deployment.yaml
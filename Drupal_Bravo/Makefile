up: storage secrets deployments services
down: delete-services delete-deployments delete-secrets delete-storage

storage:
	@kubectl apply -f ./pv.yaml
	@kubectl apply -f ./pvc.yaml

delete-storage:
	@kubectl delete -f ./pvc.yaml
	@kubectl delete -f ./pv.yaml

secrets:
	@kubectl apply -f ./drupal-mysql-secret.yaml

delete-secrets:
	@kubectl delete -f ./drupal-mysql-secret.yaml

deployments:
	@kubectl apply -f ./drupal.yaml
	@kubectl apply -f ./drupal-mysql.yaml

delete-deployments:
	@kubectl delete -f ./drupal.yaml
	@kubectl delete -f ./drupal-mysql.yaml

services:
	@kubectl apply -f ./drupal-service.yaml
	@kubectl apply -f ./drupal-mysql-service.yaml

delete-services:
	@kubectl delete -f ./drupal-service.yaml
	@kubectl delete -f ./drupal-mysql-service.yaml


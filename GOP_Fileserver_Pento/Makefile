up: storage deployment service
down: delete-service delete-deployment delete-storage

storage:
	@kubectl apply -f ./pv.yaml
	@kubectl apply -f ./pvc.yaml

delete-storage:
	@kubectl delete -f ./pv.yaml
	@kubectl delete -f ./pvc.yaml

deployment:
	@kubectl apply -f ./gop-fileserver.yaml

delete-deployment:
	@kubectl delete -f ./gop-fileserver.yaml

service:
	@kubectl apply -f ./gop-fs-service.yaml

delete-service:
	@kubectl delete -f ./gop-fs-service.yaml
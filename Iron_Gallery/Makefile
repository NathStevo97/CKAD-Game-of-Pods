up:	namespace-up db-up gallery-up network-up

down: network-down gallery-down db-down namespace-down

namespace-up:
	@kubectl apply -f iron-gallery-ns.yaml

namespace-down:
	@kubectl delete -f iron-gallery-ns.yaml

db-up:
	@kubectl apply -f ./iron-db.yaml
	@kubectl apply -f ./iron-db-svc.yaml

db-down:
	@kubectl delete -f ./iron-db-svc.yaml
	@kubectl delete -f ./iron-db.yaml

gallery-up:
	@kubectl apply -f ./iron-gallery.yaml
	@kubectl apply -f ./iron-gallery-svc.yaml

gallery-down:
	@kubectl delete -f ./iron-gallery-svc.yaml
	@kubectl delete -f ./iron-gallery.yaml

network-up:
	@kubectl apply -f ./network-policy.yaml
	@kubectl apply -f ./ingress.yaml

network-down:
	@kubectl delete -f ./ingress.yaml
	@kubectl delete -f ./network-policy.yaml


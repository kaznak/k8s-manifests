
build:
	kubectl kustomize k8s/ | renvsubst -f

apply:
	kubectl kustomize k8s/ | renvsubst -f | kubectl apply -f -

get:
	kubectl kustomize k8s/ | renvsubst -f | kubectl get -f -

delete:
	kubectl kustomize k8s/ | renvsubst -f | kubectl delete -f -

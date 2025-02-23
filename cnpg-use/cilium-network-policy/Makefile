
build:
	kubectl kustomize k8s/ | renvsubst -N

apply:
	kubectl kustomize k8s/ | renvsubst -N | kubectl apply -f -

get:
	kubectl kustomize k8s/ | renvsubst -N | kubectl get -f -

delete:
	kubectl kustomize k8s/ | renvsubst -N | kubectl delete -f -

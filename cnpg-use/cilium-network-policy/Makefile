
build:
	kubectl kustomize k8s/ | renvsubst -N

apply:
	kubectl kustomize k8s/ | renvsubst -N | kubectl apply -f -

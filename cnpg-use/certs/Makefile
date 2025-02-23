
build:
	kubectl kustomize k8s/ | renvsubst -N

deploy:
	kubectl kustomize k8s/ | renvsubst -N | kubectl apply -f -

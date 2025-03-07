
K8S_DIR := k8s

###################################################################
build:
	kubectl kustomize $(K8S_DIR) | renvsubst -f

apply:
	kubectl kustomize $(K8S_DIR) | renvsubst -f | kubectl apply -f -

get:
	kubectl kustomize $(K8S_DIR) | renvsubst -f | kubectl get -f -

delete:
	kubectl kustomize $(K8S_DIR) | renvsubst -f | kubectl delete -f -

###################################################################
$(K8S_DIR):
	mkdir -p $@

generate: generate-form-manifest

generate-form-manifest: | $(K8S_DIR)
	curl -Lf https://github.com/kubernetes-sigs/metrics-server/releases/latest/download/components.yaml |	\
		../../scripts/split-yaml $(K8S_DIR) |	\
		../../scripts/rename-k8s-manifest	|	\
		cut -d' ' -f2	| \
		../../scripts/list-to-kustomize	| \
		tee $(K8S_DIR)/kustomization.yaml

clean:
	rm -rf $(K8S_DIR)

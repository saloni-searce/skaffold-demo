kubeconfig folder : ~/.kube
gcloud auth application-default login

GCR repo : gcr.io/searce-playground/saloni-test-image

-------------------------------------------------------------------------
Working wth cluster
-------------------------------------------------------------------------

k get nodes --contect clustename
k config get contextß
k config use-context cluster-context

--------------------------------------------------------------------------
Kind commands
--------------------------------------------------------------------------

Installing Kind on Linux:-
curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.11.1/kind-linux-amd64
chmod +x ./kind
sudo mv kind /usr/local/bin

Cluster Commands :-
kind create cluster --name kind-2 (one-node cluster)
kind get clusters
kubeconfig file : cat ~/.kube/config 
kubectl cluster-info --context kind-kind
kind delete cluster

Multinode Cluster :-
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
- role: control-plane
- role: worker
- role: worker

save in : vi /tmp/kind.yaml
run the command for multicluster : kind create cluster --config kind.yaml

---------------------------------------------------------------------------
Skaffols commands 
---------------------------------------------------------------------------

kind sudo : sudo groupadd kind
sudo usermod -aG kind $USER
newgrp kind
skaffold init
skaffold dev ---- for continous deployment
skaffold run
skaffold dev -p cloudbuild --default-repo gcr.io/searce-playground --port-forward










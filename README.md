# kind
Kubernetes kind Implementierung erforschen

Gruppe:

Iryna
Mahad
Johannes

Einrichtung von Kind in einer neuen VM:

vorab:

apt update

Curl

apt install curl

Kind Installation:

https://kind.sigs.k8s.io/docs/user/quick-start/#installation

curl -Lo ./kind https://kind.sigs.k8s.io/dl/v0.17.0/kind-linux-amd64
chmod +x ./kind
sudo mv ./kind /usr/local/bin/kind

Kubernetes: Kubectl

https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/

curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

Kind starten (Single Node) mit pre built image:
-kind create cluster


mit Applikation/image festsetzen:
kind create cluster --image=nginx

Loading an image into the Cluster:
Docker pull "image"
kind load docker-image "image"



list images present on cluster node:
docker exec -it "name of the Docker container" crictl images

Cluster forensich untersuchen:

-kind export logs 

to specify a location, add a path to the directory afterthe command:
-kind exports logs ./directory


Multi Node starten:

-kind create cluster --config config-exercise.yaml

#Test

kubebuilder init --domain sklrsn.in --repo github.com/sklrsn/k8s-operator-cm

kubebuilder create api --group hello --version v1 --kind Greeter

make

make manifests

make docker-build docker-push IMG=sklrsn/greeter-operator:v1

make deploy IMG=sklrsn/greeter-operator:v1

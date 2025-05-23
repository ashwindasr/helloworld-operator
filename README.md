# helloworld-operator

A test operator that simply creates a pod and echos "Hello World". Intended to be used by the Automated Release Tooling Team to test out Brew/Konflux build/release
pipelines.

### Test Deploy on a local cluster

- Build and push the operator build to the registry of your choice, for example:

`make docker-build docker-push IMG="quay.io/rh_ee_asdas/hellworld-operator:v0.0.1"`

- Deploy the operator to the cluster, for example

`make deploy IMG=quay.io/rh_ee_asdas/hellworld-operator:v0.0.1`

- Apply the CustomResouce to start the Pod, for example: 

`oc apply -f config/samples/apps_v1alpha1_helloworld.yaml`
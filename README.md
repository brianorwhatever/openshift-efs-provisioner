This creates an AWS EFS openshift provisioner. The biggest hurdle not mentioned anywhere is that the pod has to run as root in order to create the dir that is mapped to EFS. If there is a better solution please let me know.

1. Replace the <AWS_REGION> and <EFS_FILESYSTEM_ID> entries in both `pod.yaml` and `configmap.yaml` with proper values
2. Create `efs` namespace
  `oc new-project efs`
2. Apply all files
  `oc apply -f clusterrole.yaml,clusterrolebinding.yaml,configmap.yaml,pod.yaml,role.yaml,rolebinding.yaml,serviceaccount.yaml`

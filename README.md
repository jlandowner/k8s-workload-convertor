# k8s-workload-convertor

## Usage
1.  Deployment -> DaemonSet
    
    Example: `deployment.apps/coredns` to `daemonset.apps/coredns`
    ```sh
    # Get the deployment configuration
    kubectl -n kube-system get deployment.apps/coredns -o yaml > coredns-deploy.yaml
    
    # Convert to DaemonSet. Output file is coredns-ds.yaml
    python3 k8s-workload-convertor.py convert \
        --from_kind=Deployment --from_file=coredns-deploy.yaml \
        --to_kind=DaemonSet --to_file=coredns-ds.yaml
    ```
    

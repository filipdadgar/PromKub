# PromKub
Prometheus with Grafana deployed on Kubernetes inspired by Giantswarm.

# Installation

git clone to directory
cd to directory and run kubectl create -f .

# Troubleshooting
kubectl delete namespace monitoring.

# Config 

If you are running with selfsigned CA's, add this line to prometheus-configmap.yaml:

**insecure_skip_verify: true** 

>   - job_name: 'kubernetes-nodes'
    -    tls_config:
    -      ca_file: /var/run/secrets/kubernetes.io/serviceaccount/ca.crt
    -      insecure_skip_verify: true
    -    bearer_token_file: /var/run/secrets/kubernetes.io/serviceaccount/token
    -    kubernetes_sd_configs:
>
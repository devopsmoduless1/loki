# loki Logging <br />

Prerequisites <br />
1. Kubernetes cluster <br /> 
2. Helm <br />

# Installation Steps
 Create AWS S3 bucket to store Logs of Kubernetes cluster  <br />
  Example: test-loki  <br />
   
# Create AWS Secret in Kubernetes cluster
Create AWS secret. Make sure to replace BASE64ENCODED-AWS-ACCESSKEY and BASE64ENCODED-AWS-SECRETKEY with your AWS access and secret key which is base64 encoded <br />
 kubectl create ns loki <br />
 kubectl apply -f secret.yaml    <br />

# Install Loki using helm
   helm repo add grafana https://grafana.github.io/helm-charts  <br />
   helm upgrade --install --values loki.yaml loki grafana/loki-stack --version 2.10.0 -n loki  <br />

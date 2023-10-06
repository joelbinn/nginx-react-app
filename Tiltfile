# This Tiltfile shall
# - watch the src catalog an in case of and source changes it should
# - build a new docker image based on the Docker file in this catalog
# - deploy the new docker image to the k8s cluster using the deployment and service manifests in the k8s catalog
# - and set up a port forward to the k8s service at port 18280
# Build
docker_build(
    'joelabs/my-react-app',
    context="./",
    dockerfile='./Dockerfile',
)

# Deploy
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])

# Manage
k8s_resource('my-react-app', port_forwards='18280:80')
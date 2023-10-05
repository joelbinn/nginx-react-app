# Build
custom_build(
    # Name of the container image
    ref = 'joelabs/my-react-app',
    # Command to build the container image
    command = 'npm run build && npm run docker:build',
    # Files to watch that trigger a new build
    deps = ['src']
)

# Deploy
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])

# Manage
k8s_resource('my-react-app', port_forwards=['18280'])
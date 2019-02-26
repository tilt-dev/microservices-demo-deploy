# -*- mode: Python -*-

k8s_yaml('deploy/kubernetes/manifests/sock-shop-ns.yaml')
k8s_yaml('deploy/kubernetes/complete-demo.yaml')

# Check if the microservices-demo-front-end directory exists.
if str(local("ls ../microservices-demo-front-end")).strip():
  repo = local_git_repo('../microservices-demo-front-end')
  docker_build('weaveworksdemos/front-end', repo)
else:
  print('Could not find front-end repo. Skipping!')

# -*- mode: Python -*-

k8s_yaml('deploy/kubernetes/manifests/sock-shop-ns.yaml')
k8s_yaml('deploy/kubernetes/complete-demo.yaml')

def exists(dir_name):
  return bool(str(local("ls %s || exit 0" % dir_name)).strip())

# Check if we have the front-end repo for this image on disk,
# and build it if we do.
if exists('../front-end'):
  docker_build('weaveworksdemos/front-end', '../front-end')
else:
  print('Could not find front-end repo. Skipping!')

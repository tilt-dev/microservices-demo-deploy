# -*- mode: Python -*-

k8s_yaml('deploy/kubernetes/manifests/sock-shop-ns.yaml')
k8s_yaml('deploy/kubernetes/complete-demo.yaml')

def exists(dir_name):
  return bool(str(local("ls %s || exit 0" % dir_name)).strip())

# Check if we have the repo for this image on disk,
# and build it if we do.
def build_if_exists(name):
  dir_name = "../microservices-demo-%s" % name
  image_name = "weaveworksdemos/%s" %name
  if exists(dir_name):
    docker_build(image_name, dir_name)
  else:
    print('Could not find front-end repo. Skipping!')

build_if_exists('front-end')
build_if_exists('catalogue')
build_if_exists('carts')
build_if_exists('orders')
build_if_exists('shipping')
build_if_exists('payment')
build_if_exists('user')

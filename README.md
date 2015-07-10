# openshift-registry-proxy
This pod is used when building Vagrant boxes for training classes, the
pod to proxies the OpenShift registry (port 5000) from the private to public network interface.

Below, your working tree is assumed to be named `.../origin`

When deploying:

1. Add `config.vm.network "forwarded_port", guest: 5000, host: 5000` to
   [origin/Vagrantfile](https://github.com/openshift/origin/blob/master/Vagrantfile)
2. Add `image openshift/origin-registry-proxy images/registryproxy` to
   [origin/hack/build-images.sh](https://github.com/openshift/origin/blob/master/hack/build-images.sh)
3. Copy https://github.com/jwhonce/openshift-registry-proxy/images/registryproxy/ into [origin/images](https://github.com/openshift/origin/tree/master/images)
4. Build your updated origin tree



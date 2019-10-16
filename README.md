# Tilt Operator SDK Demo

### What's in this repo?
This repo contains a simple operator that creates memcached instances when a memcached CRD is created in the cluster. It is entirely based off of the [operator-sdk getting started guide](https://github.com/operator-framework/getting-started).

This repo also contains a Tiltfile which allows you to iterate on the operator quickly. Try changing the `log` variable in `pkg/controller/memcached/memcached_controller.go` to use a different prefix and see the operator respond.

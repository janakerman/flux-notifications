# Flux-notifications

## A dropped attempt to boostrap a local Git cluster

Hacky attempt to bootstrap a local Git server with Flux

```
./install_gitsrv.sh
```

### Learnings

* K8s ephemeral containers are a thing - a dead end that wasn't necessary - enabled as an additional feature gate
* Projected volume allows you to mount multiple secrets as files in the same dir
* Mounting an incorrectly formatted `.pub` key stops SSH access (e.g with contents `placeholder`).
* `go-git` seems to not handle URL correctly `ssh://git@localhost/~/cluster` (recommended by Flux docs) - [issue](https://github.com/go-git/go-git/issues/430)

## Notifications ideas

* Consistent metadata between source-controller and notification-controller to easily tie events to a reference
* reportingController's labels to be able to identify specific clusters when consuming events from many clusters?

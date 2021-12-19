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

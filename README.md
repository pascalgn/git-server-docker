# git-server-docker

Simple git server for testing purposes.

Serves a single git repository via HTTP without any authentication.

## Usage

Docker:

```sh
docker run -p 3000:3000 pascalgn/git-server-docker
git clone http://localhost:3000/repository.git
```

Kubernetes:

```sh
kubectl create -f https://raw.githubusercontent.com/pascalgn/git-server-docker/master/kubernetes.yaml
PORT=$(kubectl get service/git-server -o jsonpath={.spec.ports[0].nodePort})
git clone http://localhost:${PORT}/repository.git
```

## Acknowledgements

This is just a wrapper around
[node-git-http-server](https://github.com/bahamas10/node-git-http-server)
which is based on
[git-http-backend](https://github.com/substack/git-http-backend).

## License

MIT

# freeswitch-kubernetes
Kubernetes configs for Freeswitch

You need to bind the PVC to a node. If you don't have a node, bind it to the default cluster node with

```sh
sudo kubectl get nodes -o=custom-columns=NAME:.metadata.name --no-headers | head -n 1 | xargs -I {} sudo kubectl label node {} namespace/node_label=true
```

and in your config file replace `NODE_NAME` with your newly created node label

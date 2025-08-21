# kubectl Productivity

## Quick Context Switch
```
kubectl config use-context <name>
```

## Wide Output Alias
```
alias kx='kubectl get pods -o wide'
```

## JSONPath Extract
```
kubectl get pod POD -o jsonpath='{.status.phase}'
```

> TODO: Add krew plugin recommendations.

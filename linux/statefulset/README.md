## 1. create a stateful set with azure file mount
```kubectl create -f https://raw.githubusercontent.com/andyzhangx/Demo/master/linux/statefulset/statefulset-azurefile.yaml```

#### watch the status of pod until its `Status` changed from `Pending` to `Running`
```watch kubectl describe po statefulset-azurefile```

#### enter the pod container to do validation
```kubectl exec -it statefulset-azurefile-0 -- bash```


## 2. create a stateful set with azure disk mount
```kubectl create -f https://raw.githubusercontent.com/andyzhangx/Demo/master/linux/statefulset/statefulset-azuredisk.yaml```

#### watch the status of pod until its `Status` changed from `Pending` to `Running`
```watch kubectl describe po statefulset-azuredisk```

#### enter the pod container to do validation
```kubectl exec -it statefulset-azuredisk-0 -- bash```

### Note:
1. azure disk only supports RWO, so only one replica is allowed for a stateful set with azure disk mount
2. azure file supports RWX, multiple replicas are allowed for a stateful set with azure file mount
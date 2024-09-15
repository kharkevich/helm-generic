# helm-generic
Generic Helm charts

## Notes

### common library
Common library inspired by [helm common](https://github.com/helm/charts/blob/master/incubator/common/README.md)

### Ingress notes

[Gateway API](https://kubernetes.io/docs/concepts/services-networking/gateway/) is recommended way to expose application outside

Some example:

```yaml
kind: HTTPRoute
apiVersion: gateway.networking.k8s.io/v1
metadata:
  name: application-name
  namespace: application-namespace
spec:
  parentRefs:
    - kind: Gateway
      name: default-internal
      namespace: gateway-namespace
  hostnames:
    - k8s.technicaldomain.xyz
  rules:
    - matches:
        - path:
            type: PathPrefix
            value: "/"
      backendRefs:
        - name: application-service
          port: 80
```


### icons
Icons made by [Good Ware](https://www.flaticon.com/authors/good-ware "Good Ware") from [www.flaticon.com](https://www.flaticon.com/ "Flaticon")

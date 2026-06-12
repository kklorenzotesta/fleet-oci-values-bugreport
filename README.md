# GitRepo

```yaml
apiVersion: fleet.cattle.io/v1alpha1
kind: GitRepo
metadata:
  name: fleet-oci
  namespace: fleet-local
spec:
  repo: "https://github.com/kklorenzotesta/fleet-oci-values-bugreport.git"
  branch: main
```

# Bug

On fleet `0.15.2` and `0.15.3-rc.1` the bundle creation jobs fails with:

```
time="2026-06-12T09:17:24Z" level=warning msg=".: no resources found to deploy"
{"fleetErrorMessage":"no resource found at the following paths to deploy: [.]","level":"fatal","msg":"Fleet cli failed","time":"2026-06-12T09:17:24Z"}
```

On fleet `0.16.0-alpha.10` it works correctly.

Removing the `valuesFiles` from the `fleet.yaml` makes it work also on `0.15.2` and `0.15.3-rc.1`.

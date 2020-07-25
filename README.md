# inject-k8s-secrets

This is a bash helper script that:
- Retrieves AWS Secrets Manager Secrets with the aws cli under a given prefix (defined at top of script)
- Converts the secrets from the form `some/secret/thing` into Kubernetes-friendly secret name format: `some-secret-thing`
- Inject the secrets into the k8s cluster using `kubectl`

## Usage

```
./inject.sh cluster namespace region profile
```

**Example**

```
./inject.sh foocluster app us-west-2 someawsprofilename
```

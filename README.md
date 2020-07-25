# inject-k8s-secrets
Bash script to inject AWS Secrets Manager Secrets into Kubernetes secrets.

## Usage

```
./inject.sh cluster namespace region profile
```

example:

```
./inject.sh foocluster app us-west-2 someawsprofilename
```

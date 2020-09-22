# inject-k8s-secrets

This is a bash helper script that:
- Retrieves AWS Secrets Manager Secrets with the aws cli under a given prefix
- Converts the secret name format into Kubernetes-friendly naming
- Inject the secrets into the k8s cluster using `kubectl`

See my related article: [Injecting Secrets from AWS Secrets Manager into Kubernetes](https://medium.com/@jashby2/injecting-secrets-from-aws-secrets-manager-into-kubernetes-9aad3c98e078)

## Usage

```
./inject.sh secret_prefix cluster namespace region profile
```

**Example**

```
./inject.sh myapp/dev foocluster app us-west-2 someawsprofilename

Injecting all secrets under myapp/dev from AWS Secrets Manager into cluster foocluster, namespace app

AWS Secret name                                   ----> k8s Secret Name
====================                                    ====================
myapp/dev/api/db/dbpass                                 api-db-dbpass
myapp/dev/api/api_key_foo                               api-api-key-foo
myapp/dev/parser/backend/redis-pw                       parser-backend-redis-pw
```

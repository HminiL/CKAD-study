# Note on Secrets

- Secret are not Encrypted, they are just Base64 encoded
  - Do not check-in secrets to git or any other VCS

- Secrets are not encrypted in ETCD
  - Enable encryption at rest for ETCD

- Anyone able to create pods/deployments in the same namespace can access the secrets
  - Configure least-privilege access to Secrets - RBAC

- Consider third-party secrets store provider
  - AWS Provider, Azuer Provider, GCP Provider, Vault Provider, etc.
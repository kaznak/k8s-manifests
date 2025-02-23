# cnpg-certs

Certificates for [CloudNativePG](https://cloudnative-pg.io/) based on [cert-manager](https://cert-manager.io/).

This manifests include:

- Selfsigned Certificate Authority
- Client Certificates

Server Certificate is not included that is included in the cluster manifests.

Parameters:

- APP_NAME
- NAMESPACE

## Note

If the selfsigned issuer is used as the CA, the certificates that CA issued are selfsigned.
It causes some trouble. Thus this manifest creates a CA(cert-ca) from the selfsigned issuer(cert-root).

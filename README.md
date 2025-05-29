# Custom Keycloak 26.2.4 with Kerberos Tools

Cette image Docker est basée sur Keycloak 26.2.4 et inclut les outils Kerberos :

- `kinit`, `klist`, `ktutil`, `kdestroy`
- `dig`, `host`, `nslookup`, `tcpdump`
- `curl`, `hostname`, `ping`, etc.

## Utilisation

```bash
docker run -d \
  --name keycloak-kerb \
  -e KEYCLOAK_ADMIN=admin \
  -e KEYCLOAK_ADMIN_PASSWORD=admin \
  -v /etc/krb5.conf:/etc/krb5.conf:ro \
  -v /etc/keycloak.keytab:/etc/keycloak.keytab:ro \
  -p 8080:8080 \
  ghcr.io/<ton_utilisateur_github>/custom-keycloak:26.2.4 start-dev

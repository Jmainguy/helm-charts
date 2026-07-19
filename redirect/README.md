# redirect

Istio HTTPS redirect chart: Certificate + Gateway + VirtualService, no pods.

## Values

| Key | Description |
|-----|-------------|
| `virtualService.hosts` | Hostnames that terminate TLS and redirect |
| `redirect.authority` | Target host (e.g. `ahhc.org`) |
| `redirect.scheme` | Target scheme (default `https`) |
| `redirect.redirectCode` | HTTP redirect code (default `301`) |
| `cert.issuer` | cert-manager ClusterIssuer (default `letsencrypt-http`) |

## Example

```yaml
name: augustine-care
virtualService:
  hosts:
    - augustine.care
    - www.augustine.care
redirect:
  authority: ahhc.org
  scheme: https
  redirectCode: 301
```

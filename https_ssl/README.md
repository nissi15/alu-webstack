# HTTPS SSL

Pointing subdomains to the web stack servers and serving the site over HTTPS,
with HAProxy terminating SSL on the load balancer.

## Servers

| Name | IP |
| ---- | -- |
| 7301-web-01 | 18.130.10.200 |
| 7301-web-02 | 3.8.211.28 |
| 7301-lb-01 | 13.40.42.89 |

## Files

| File | Description |
| ---- | ----------- |
| `0-world_wide_web` | Displays the record type and destination of a domain's subdomains |
| `1-haproxy_ssl_termination` | HAProxy config that accepts HTTPS on port 443 and passes it to the web servers |
| `2-redirect_http_to_https` | HAProxy config that also redirects all HTTP traffic to HTTPS with a 301 |

## Usage

```
$ ./0-world_wide_web example.com
$ ./0-world_wide_web example.com web-02
```

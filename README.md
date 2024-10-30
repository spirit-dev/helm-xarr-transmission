# Welcome to gitlab

[![App Status](https://argocd-internal.spirit-dev.net/api/badge?name=transmission-turingpi&revision=true&showAppName=true)](https://argocd-internal.spirit-dev.net/applications/transmission-turingpi)

## Table of content

[[_TOC_]]

## Installation process

The installation is entirely managed by Argocd.

A `Makefile` is present here to ease the first and one-time deployment or in case of an issue.
The installation should be done in two steps:

```shell
#> make dry-run ENV=<ENV>
#> make install ENV=<ENV>
```

## Exemples

During a debugging session, i've created some examples to debug certain aspects of Transmission X OpenVPN

- [gluetun-sidecar](examples/transmission-sidecar/Readme.md)

## Env var

Here is a list of interesting environment variables:

```yaml
# - name: TR_CURL_VERBOSE
#   value: "true"
# - name: CURL_CA_BUNDLE
#   value: "/etc/ssl/certs/ca-certificates.crt"
# - name: LOCAL_NETWORK
#   value: 192.168.0.0/16
- name: ENABLE_UFW
  value: "false"
- name: UFW_ALLOW_GW_NET
  value: "false"
- name: UFW_EXTRA_PORTS
  value:
- name: UFW_DISABLE_IPTABLES_REJECT
  value: "false"

- name: TRANSMISSION_DHT_ENABLED
  value: "false"
- name: TRANSMISSION_PEX_ENABLED
  value: "false"
```

a complete list of interesting vars is available [here](https://github.com/truecharts/charts/blob/master/charts/stable/transmission/values.yaml)

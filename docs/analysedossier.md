# Analysedossier — Final Assessment Cloud Infrastructure

<!-- Vul elke sectie aan. Hernoem de koppen niet: de automatische controle zoekt ze.
     Screenshots zet je in docs/images/ en voeg je toe met ![beschrijving](images/bestand.png).
     Toon nooit gevoelige waarden (tokens, wachtwoorden, kubeconfig) op een screenshot. -->

## Architectuur

Je applicatie en een architectuurschema: cloudresources, nodes, netwerk, namespaces, ingress/tunnel, VPN, monitoring.

## Cloudinfrastructuur

Terraform/OpenTofu: welke resources, variabelen en outputs? Screenshots van `tofu apply` en `kubectl get nodes -o wide`.

## Ansible

Inventory en playbooks: wat beheer je ermee? Screenshot van een tweede run met `changed=0`.

## Deployment

Stappenplan met commando's: hoe deploy je alles, en hoe test iemand anders het? Screenshot van `kubectl get pods -o wide`.

## Helm en omgevingen

Structuur van je chart; verschillen tussen test en productie. Screenshot van de Helm-releases per omgeving.

## Schaalbaarheid

Replicas, `topologySpreadConstraints` en je HPA. Screenshot van de HPA die opschaalt onder belasting.

## HTTPS

Ingress (Traefik) of Cloudflare tunnel: hoe ingesteld? Screenshot van de site via HTTPS.

## Extra features

Onderzoek naar Traefik, Vault, WireGuard en Cloudflare: welke heb je gebruikt, waarom (niet), en hoe? Screenshots.

## Monitoring

Externe monitoring: tool, wat meet je, welke alerts? Screenshots van het dashboard en een alert.

## Conclusies

Je belangrijkste keuzes, hun nadelen, en wat je zou verbeteren.

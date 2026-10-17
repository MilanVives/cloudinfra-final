# Ansible

- `inventory/`: je cloud-VM's/nodes (statisch, of gegenereerd uit Terraform-outputs).
- `playbooks/`: installaties, configuratie en Helm-deploys (`kubernetes.core.helm`).
- `requirements.yml`: de collecties die je playbooks gebruiken.

De automatische controle installeert `requirements.yml`, doet `ansible-playbook --syntax-check` en `ansible-lint`.
Playbooks zijn idempotent: een tweede run geeft `changed=0`.

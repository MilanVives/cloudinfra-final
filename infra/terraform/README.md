# Terraform / OpenTofu

Je cluster (≥ 3 worker nodes + control plane) en extra cloudresources, als code.

- `tofu fmt` en `tofu validate` moeten slagen (de automatische controle doet `tofu init -backend=false`).
- Geen tokens in de code: gebruik variabelen (`sensitive = true`) en commit enkel `terraform.tfvars.example`.
- **Commit nooit** `*.tfstate` of een `terraform.tfvars` met secrets.

# Cloud Infrastructure — eindopdracht

Dit is jouw repository voor de **Final Assessment** van Cloud Infrastructure (VIVES, 3CYB).
De volledige opdracht staat op de cursussite.

> ⚠️ Werk in **deze** repository (`VivesMDima/2627-cloudinfra-ti-final-<jouw-username>`), die je via je eigen accept-link kreeg — niet in de template-repository waarop ze gebaseerd is.

## Snel starten

1. Kopieer `app/` en `k8s/` uit je projectrepository (PE1) naar hier.
2. Vul `project.yaml` in, ook `live_url` (de HTTPS-URL van je productie-omgeving).
3. Cluster als code in `infra/terraform/`, beheer met Ansible in `ansible/`.
4. Helm chart in `helm/app/`. **`templates/nodeinfo.yaml` niet verwijderen** en `/nodeinfo` via je ingress/tunnel routeren.
5. Externe monitoring in `monitoring/`; schrijf `docs/analysedossier.md`, screenshots in `docs/images/`.
6. Dien in: `./scripts/submit.sh` (Windows: in **Git Bash**). Je resultaat verschijnt onder **Releases**.

## Links

- Productie: _vul aan_
- Test: _vul aan_
- Monitoring-dashboard: _vul aan_

## Automatische controles

De controles zijn een **vangnet**: een FAIL wijst op een probleem dat ook in de beoordeling meetelt.
Een volledige PASS garandeert geen maximumscore — de docent beoordeelt het geheel.

### F-R0: project.yaml ingevuld

`naam`, `studentennummer`, `github` en `live_url` zijn ingevuld.

### F-R1: Terraform geldig

`tofu fmt -check` en `tofu validate` slagen in `infra/terraform/`.

### F-R2: Ansible geldig

`ansible/inventory/` bevat hosts, de collecties uit `ansible/requirements.yml` installeren, en je playbooks slagen voor `ansible-playbook --syntax-check` en `ansible-lint`.

### F-R3: Helm chart geldig

`helm lint` en `helm template` met `values-test.yaml` én `values-prod.yaml` slagen, de output is geldig volgens `kubeconform -strict`, en er zijn naast `nodeinfo` minstens 3 workloads.

### F-R4: Schaalbaarheid geconfigureerd

In productie: elke Deployment (behalve de database) heeft minstens 2 replicas en `topologySpreadConstraints`, en er is een HorizontalPodAutoscaler.

### F-R5: Geen gecommitte secrets

`gitleaks` vindt niets in de volledige Git-geschiedenis, en er staat geen `*.tfstate` in de repository.

### F-R6: Live via HTTPS

`live_url` antwoordt met HTTP 200 over HTTPS met een geldig certificaat.

### F-R7: Multi-node

`live_url/nodeinfo` toont minstens 3 verschillende nodes.

### F-R8: Analysedossier volledig

`docs/analysedossier.md` heeft alle verplichte koppen en minstens 8 screenshots die in de repository staan.

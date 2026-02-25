``` bash

infra/
  README.md
  versions.tf                  # provider + TF/OpenTofu version constraints
  .terraform.lock.hcl
  docs/
    architecture.md
    runbooks/
      incident.md
      rotate-secrets.md
  modules/                      # reusable building blocks
    vpc/
      main.tf variables.tf outputs.tf README.md
    eks/
    rds/
    cloudwatch-alarms/
    iam-roles/
  envs/
    dev/
      main.tf                   # composes modules for dev
      variables.tf
      outputs.tf
      backend.tf                # remote state config (or partial config)
      dev.tfvars
    staging/
      ...
    prod/
      ...
  policies/
    opa/                        # optional: policy-as-code (Conftest/OPA)
    sentinel/                   # optional
  scripts/
    fmt.sh
    validate.sh
    plan.sh
    apply.sh
  .github/workflows/
    ci.yaml                     # fmt/validate/plan on PR
    cd.yaml

```

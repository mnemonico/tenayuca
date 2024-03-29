#### Steps
    - fill the file tfvars/backendvars.yml
    - fill the file tfvars/infrastructure.tfvars
    - place yourself in the `tenayuca/backendgenerator` folder
    - execute the `python main.py`
    - check the tfbackend/bootstrap.hcl and tfbackend/infrastructure.hcl
    - for bootstrap infra
        - do the `terraform init -backend-config=backend.hcl`
    - for infrastructure main infra
        - do the `terraform init -backend-config=../tfbackend/infrastructure.hcl`
    - start checking your linting `docker run --rm -v $(pwd):/data -t ghcr.io/terraform-linters/tflint --recursive`
    - start your developing `terraform plan --var-file ../tfvars/infrastructure.tfvars`
# Panenco GCP Deploy action with version remover

> Use this action to deploy GCP action and remove old versions

## Inputs

### `credentials_json`

**Required** GCP Service account JSON credentials file.

1. GCP IAM
2. Service Accounts
3. Create deployer if not exists
4. Keys (in new deployer role)
5. Add key
6. Create key
7. JSON.

### `service_id`

**Required** The ID of the app engine service.

### `project_id`

**Required** The ID of the app engine service.

### `app_yaml_path`

**Required** The path to the GCP app.yaml file.

### `extra_deploy_args`

Extra arguments to use when deploying the application.

## Action Example

```yaml
on: [push]
jobs:
  deploy_job:
    runs-on: ubuntu-latest
    name: deploy
    steps:
      - name: Deploy to app engine
        uses: Panenco/gcp-deploy@v1
        with:
          credentials_json: "{{ secrets.gcp_credentials_json }}"
          service_id: "{{ inputs.gcp_service_id }}"
          project_id: "{{ inputs.gcp_project_id }}"
          app_yaml_path: "staging.yml"
```

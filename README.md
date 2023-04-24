# Panenco GCP Deploy action with version remover

> Use this action to deploy GCP action and remove old versions

## Inputs

### `workload_identity_provider`

**Required** The [workload identity provider](https://cloud.google.com/iam/docs/workload-identity-federation)

### `service_account`

**Required** GCP service account

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
        uses: Panenco/gcp-deploy-action@v2
        with:
          workload_identity_provider: "{{ secrets.WORKLOAD_IDENTITY_PROVIDER }}"
          service_account: "{{ secrets.SERVICE_ACCOUNT }}"
          service_id: "{{ secrets.GCP_SERVICE_ID }}"
          project_id: "{{ secrets.GCP_PROJECT_ID }}"
          app_yaml_path: "staging.yml"
```

# helm-argo-rollout
Helm Chart with Argo Rollout Blue/Green Strategy

## Usage

This Helm chart is designed to make use of Argo Rollout Blue/Green Strategy applicable to any application.

- Replace all strings "app-name" in all files with the name of your application. Example:

```javascript
name: app-name #change this to the name of your app
```
- Edit values.yaml base on your setup. Look at those lines with comment **#change this** 

## Gitlab

If you are using Gitlab, refer to the .gitlab-ci.yml as guidance. Customize it based on your environment.

The following is a feature to extract the app-version and app-name from the chart so that the helm chart package is named appropriately.

```javascript
before_script:
  - export HELM_CHART_VERSION=$(awk '/^version:/ {print $2}' app-name/Chart.yaml) #extract the helm chart version
  - export HELM_CHART_NAME=$(awk 'NR==2 {print $2}' app-name/Chart.yaml) #extract the helm chart name
```


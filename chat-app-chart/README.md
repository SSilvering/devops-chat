## Helm chart for deploying chat app with mysql as database

* Install the chart
```sh
    helm install chat .
```

* Mysql monitoring configuration:
  Uncomment those lines in the values file:
```sh
mysql:
    ...
    metrics:
      enabled: true
      serviceMonitor: 
        enabled: true
        additionalLabels: ## The labels need to be set up for prometheus to scrape mysql metrics.
          release: prometheus 
```
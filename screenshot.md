# Trend deployment screenshots

These screenshots document the recorded Trend deployment, from the local Docker test through continuous health monitoring. See the [README](README.md) for setup instructions and submission details.

## Local Docker smoke test

Docker exposes port 3000. The health endpoint returned `ok` and the homepage returned HTTP 200.

![Local Docker smoke test](docs/screenshots/local-docker.jpg)

## Terraform provisioning

Terraform reported a successful apply and printed the EKS cluster and Jenkins instance outputs.

![Terraform provisioning](docs/screenshots/terraform-apply.jpg)

## GitHub push delivery

GitHub recorded an HTTP 200 response for a signed `push` delivery.

![GitHub push delivery](docs/screenshots/github-webhook.jpg)

## Jenkins deployment

The pipeline finished successfully and printed the application URL and Network Load Balancer ARN.

![Jenkins deployment](docs/screenshots/jenkins-deploy.jpg)

## EKS workload health

The cluster was `ACTIVE`, its worker was `Ready`, and both Trend replicas were available.

![EKS workload health](docs/screenshots/eks-status.jpg)

## Trend on port 3000

The Trend storefront loaded through the AWS Network Load Balancer.

![Trend on port 3000](docs/screenshots/trend-application.jpg)

## Prometheus monitoring

Blackbox Exporter probed the public health endpoint. The Prometheus graph shows `probe_success = 1`.

![Prometheus monitoring](docs/screenshots/prometheus-health.jpg)

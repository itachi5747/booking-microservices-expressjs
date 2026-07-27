# Kubernetes Manifests

This folder contains the Kubernetes manifests for the full booking stack:

- `identity`
- `flight`
- `passenger`
- `booking`
- `postgres`
- `rabbitmq`
- `otel-collector`
- `jaeger`
- `zipkin`

## Apply

From the repo root:

```bash
kubectl apply -k deployments/kubernetes
```

## Ingress

The ingress routes requests by path on `booking.local`:

- `/identity`
- `/flight`
- `/passenger`
- `/booking`

If you are testing locally, point `booking.local` to your ingress controller address.

## Notes

- The app images are referenced by the local tags produced by the Dockerfiles.
- Postgres and RabbitMQ use persistent volume claims.
- The app services read their runtime configuration from the shared ConfigMap and Secret.

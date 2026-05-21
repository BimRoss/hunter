# hunter

Lightweight travel tracker served at https://hunter.makeacompany.ai.

Data lives in the browser (localStorage) — no backend. v1 is a single HTML file behind nginx.

## Stack

- `index.html` — the app.
- `Dockerfile` — `nginx:1.27-alpine` + the file.
- `.github/workflows/build.yml` — builds + pushes `geeemoney/hunter:<version>` to Docker Hub on tag.
- Cluster manifests live in [`BimRoss/rancher-admin`](https://github.com/BimRoss/rancher-admin) under `admin/apps/hunter/`.

## Releasing

```sh
git tag -a v0.1.0 -m "v0.1.0"
git push origin v0.1.0
# bump the image tag in rancher-admin/admin/apps/hunter/deployment.yaml via PR
```

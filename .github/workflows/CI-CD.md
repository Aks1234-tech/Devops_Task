CI / CD for this repository

This repo includes two GitHub Actions workflows:

- `.github/workflows/ci.yml` — runs frontend build and installs backend dependencies on pushes and PRs.
- `.github/workflows/deploy.yml` — builds the frontend and deploys to a remote server via SSH+rsync when commits are pushed to `main`/`master`.

Required repository Secrets (set in Settings → Secrets → Actions):

- `SSH_PRIVATE_KEY` — private key for SSH access to deployment host (no passphrase recommended for CI). Add the corresponding public key to `~/.ssh/authorized_keys` for the remote user.
- `REMOTE_USER` — SSH username on the deployment host.
- `REMOTE_HOST` — hostname or IP of the deployment host.
- `REMOTE_PATH` — target path on remote where the frontend static files should be copied (for example: `/var/www/html/`).
- Optional: `REMOTE_PORT` — SSH port (defaults to `22`).
- Optional: `REMOTE_BACKEND_PATH` — if set, the backend folder will be rsynced to this path and `docker-compose up -d --build` will be attempted there.

Notes and assumptions:

- The deploy workflow expects the remote host to accept the provided SSH key and to allow the deploy user to restart Apache (via `sudo systemctl restart apache2`) or for the service command to be available.
- If your backend runs under systemd or another mechanism, adjust the restart command in `.github/workflows/deploy.yml` accordingly.
- For more advanced flows (container registry push, Kubernetes), you can adapt the workflows to build and push images and trigger your k8s manifests.

If you want, I can:

- Add a workflow step to push backend Docker images to Docker Hub or GHCR.
- Add automatic tests / linters for the backend and frontend.
- Create a small remote helper script to make restart commands idempotent on the server.

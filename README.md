# GiteaDockerized
Gitea with embedded Postgres database, Caddy web server with CloudFlare DNS challenge and Act Runner.

## Usage
1. Navigate in the `/opt` folder `cd /opt`.
2. Clone this repository using `git clone https://github.com/NicklasMatzulla/GiteaDockerized.git`.
3. Navigate in the downloaded folder using `cd GiteaDockerized/`.
4. Edit the `caddy/Caddyfile` file using `nano caddy/Caddyfile`, replace `<cloudflare_token>` with your CloudFlare [API token](https://dash.cloudflare.com/profile/api-tokens). Save the configuration by pressing `CTRL + X`, `Y` and `ENTER`.
5. Start the Gitea installation by running the command `docker compose up -d gitea postgres caddy`.
6. Open the website `https://git.your-domain.tld` and run the installation.
7. Enter the runner registration token in the `docker-compose.yml` file using `nano docker-compose.yml` for the configuration option `GITEA_RUNNER_REGISTRATION_TOKEN`. You can find it on the Gitea administration interface (`git.your-domain.tld/admin/actions/runners`). Also enter a suitable name for the runner for the configuration option `GITEA_RUNNER_NAME`. Save the configuration by pressing `CTRL + X`, `Y` and `ENTER`.
8. Enter your local IP address or that of your host in the `runner/config.yml` file using `nano runner/config.yml`. Save the configuration by pressing `CTRL + X`, `Y` and `ENTER`.
9. Start the runner using `docker compose up -d`.

If you still have problems do not hesitate to [open an issue](https://github.com/NicklasMatzulla/GiteaDockerized/issues/new).
# Getting Started

Once you are all setup and ready to go you should be able to load Organizr at [http://{{ domain }}/](http://{{ domain }}/).

If you see `{ domain }` in the link above, you are either viewing these docs on the hosted GitLab pages and not actually through HomelabOS, or something is configured incorrectly.

## File locations
HomelabOS sets up `/var/homelabos` on your server

## Using Organizr

You can click the `Settings` link, then `Edit Tabs` to be able to add links to all the various HomelabOS services.

In the very near future, HomelabOS will provision these tab links for you automatically.

The URLs for all the services can be found in their individual documentation section.

## HTTPS via LetsEncrypt

HomelabOS will use Traefik's built in LetsEncrypt integration to automatically generate SSL certificates for your various services. If initially some of the certificates don't appear valid, you have likely run into [LetsEncrypt rate limits](https://letsencrypt.org/docs/rate-limits/). Unfortunately the only fix we have for that right now is 'wait a week'.

# Homelab Commands

`[client]$ make` - Deploys HomelabOS to the server 

`[client]$ make config` - Creates the settings/config.yml file and populates it with basic information

`[client]$ make config_reset` - Resets all local settings

`[client]$ make develop` - Spins up a development stack

`[client]$ make docs_build` - Builds the HomelabOs Documentation - Requires mkdocs with the Material Theme

`[client]$ make git_sync` - Syncs user settings to a git repo

`[client]$ make lint` - Run linting scripts

`[client]$ make logo` - Displays the HomelabOS logo, and checks the version

`[client]$ make build` - Builds the HomelabOS deploy docker image

`[client]$ make remove_one <service>` - Removes the specified service e.g. `[client]$ make remove_one inventario`

`[client]$ make restart` - Restarts all enabled services

`[client]$ make restart_one <service>` - Restarts the specified service e.g. `[client]$ make restart_one inventario`

`[client]$ make reset_one <service>` - Resets the specified service's data e.g. `[client]$ make reset_one inventario`

`[client]$ make restore` - Restores a server with the most recent backup. Assuming Backups were running.

`[client]$ ./set_setting.sh <setting> <value>` - Sets the setting to value, e.g. `[client]$ ./set_setting.sh enable_organizr True`

`[client]$ ./get_setting.sh <setting>` - Displays the current setting of value, e.g. `[client]$ ./get_setting.sh enable_organizr`


`[client]$ make tag <tag>` - Runs just the items tagged with a specific tag e.g. `[client]$ make tag tinc`

`[client]$ make terraform` - Spin up cloud servers with Terraform [See documentation](https://gitlab.com/NickBusey/HomelabOS/blob/dev/docs/setup/terraform.md)

`[client]$ make terraform_destroy` - Destroy servers created by Terraform

`[client]$ make update` - Skips the initial setup and updates HomelabOS services

`[client]$ make update_one <serive>` - Updates just one HomelabOS service e.g. `[client]$ make update_one inventario`

`[client]$ make uninstall` - Removes HomelabOS services


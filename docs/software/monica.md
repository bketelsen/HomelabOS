# Monica

[Monica](https://www.monicahq.com/) is an open source personal CRM.

## Configuration

This requires some manual setup unfortunately.

First make sure all the migrations have completed and that accessing the Monica URL below renders a login page.

Once that is done, login to your server and stop the services with `systemctl stop homelabos`

Spin up a monica specific app by CDing into the HomelabOS Docker folder `cd /var/homelabos/docker` and then running `docker-compose run monicahq shell`

Once you are inside the Docker container, run `php artisan setup:production` then after that's done `exit` the container. Now you should spin down the DB container left running with `docker stop docker_monicahq_db_1`.

NOW you should be able to access the Monica URL below again, and be presented with a registration page for the first account.

## Access

Monica is available at [https://monica.{{ domain }}/](https://monica.{{ domain }}/) or [http://monica.{{ domain }}/](http://monica.{{ domain }}/)

{% if enable_tor %}
It is also available via Tor at [http://monica.{{ tor_domain }}/](http://monica.{{ tor_domain }}/)
{% endif %}

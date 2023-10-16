# Docker (NGINX + PHP-FPM + MySQL + Redis + Mailpit)

This Docker env is build to speed up the development of PHP applications.\
It uses The latest PHP versions, older versions when build we be available in the future by branches and/or tags.\

## Requirements
- Docker desktop
- Docker compose

## Usage
- Clone this repo
- Place your project code inside the `app` folder
- Copy and rename the `default.conf.example` file to `default.conf` and configure it to your needs (file is found inside `./docker/nginx/`)
- Run `docker-compose up -d`
- Open your browser and go to `http://localhost`
- Enjoy!

## Services
- NGINX (latest)
- PHP-FPM (8.2)
- MySQL (latest)
- Redis (latest)
- Mailpit (latest)

## PHP Extensions
You can edit and see the PHP extensions that are installed in the `./docker/php/Dockerfile` file.

## Permission issues
If you have permission issues with the `app` folder, you can run the following command to fix it:
- Inside the php container: `chmod 775 -R /var/www/html && chown -R :www-data /var/www/html`
- Inside your own terminal: `chown -R {your-user-name} app`
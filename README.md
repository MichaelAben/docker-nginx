# Docker (NGINX + PHP-FPM + MySQL + Redis + Mailpit)

This Docker env is build to speed up the development of PHP applications.\
It uses The latest PHP versions, older versions when build we be available in the future by branches and/or tags.

## Requirements
- Docker desktop (https://www.docker.com/products/docker-desktop)

## Usage
- Clone this repo
- Place your project code inside the `app` folder
- Copy and rename the `default.conf.example` file to `default.conf` and configure it to your needs (file is found inside `./docker/nginx/`)
- Run `docker-compose up -d`
- Open your browser and go to `http://localhost`
- Enjoy!

## Services
- NGINX (latest) (container-name: nginx)
- PHP-FPM (8.2) (container-name: php)
- MySQL (latest) (container-name: mysql)
- Redis (latest) (container-name: redis)
- Mailpit (latest) (container-name: mailpit)

## Debugging PHP
Xdebug is installed and configured to work with any IDE that supports it and uses default configuration.\
In PhpStorm you will get a message if the debugger is configured correctly.\
Xdebug configuration can be edited inside the `./docker/php/local.ini` file.

## Locale
The locale is set to `nl_NL.UTF-8` by default.\
You can change this in the `./docker/php/local.ini` file. And the `./docker/php/dockerfile` file.
Timezone can be edited inside `./docker/php/dockerfile` file.

## Connecting to containers inside others
Use the container name as the host name.\
Example: `mysql` is the host name for the MySQL container.

If you wish to connect to containers from your local machine, you can add `127.0.0.1 {container-name}` (replace
{container-name} with the name of the container) to your hosts file.

## Ports
All ports are the default ports for each service.

## PHP Extensions
You can edit and see the PHP extensions that are installed in the `./docker/php/Dockerfile` file.

## Permission issues
If you have permission issues with the `app` folder, you can run the following command to fix it:
- Inside the php container: `chmod 775 -R /var/www/html && chown -R :www-data /var/www/html`
- Inside your own terminal: `chown -R {your-user-name} app`

## Need support?
Open an issue on the repo and I will try to help you as soon as possible.

## Contributing
If you wish to contribute to this project, feel free to open a pull request.

## License
This project is licensed under the MIT license. Which means you can do whatever you want with it.
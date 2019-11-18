# Nginx Web Server

Nginx & PHP 7 web server.

## PHP Application Quick Run

You can get up and running with a PHP application inside Docker in minutes.

- Run the command on your project root to start a docker container and attach the application. 
```
$ docker run -d -p 5000:80 --name=my-app-name -v $PWD:/var/www/public avonnadozie/nginx-php-server
```
For projects and frameworks with public files separated to a `public` folder
```
$ docker run -d -p 5000:80 --name=my-app-name -v $PWD:/var/www avonnadozie/nginx-php-server
```

- Visit the Docker container URL [http://0.0.0.0:5000](http://0.0.0.0:5000)

### Arguments

Here are some arguments

- `NGINX_HTTP_PORT` - HTTP port. Default: `80`.
- `NGINX_HTTPS_PORT` - HTTPS port. Default: `443`.
- `COMPOSER_HASH` - Composer hash. Default: `a5c698ffe4b8e849a443b120cd5ba38043260d5c4023dbf93e1558871f1f07f58274fc6f4c93bcfd858c6bd0775cd8d1`.
- `PHP_VERSION` - The PHP version to install. Supports: `7.3`. Default: `7.3`.
- `ALPINE_VERSION` - The Alpine version. Supports: `3.9`. Default: `3.9`.

### Environment Variables

Here are some configurable environment values.

- `WEBROOT` – Path to the web root. Default: `/var/www`
- `WEBROOT_PUBLIC` – Path to the web root. Default: `/var/www/public`
- `PRODUCTION` – Is this a production environment. Default: `0`
- `PHP_MEMORY_LIMIT` - PHP memory limit. Default: `128M`
- `PHP_POST_MAX_SIZE` - Maximum POST size. Default: `50M`
- `PHP_UPLOAD_MAX_FILESIZE` - Maximum file upload file. Default: `10M`.
- `STARTUP_SCRIPT` - Optional script to run after container starts. Path should be an absolute path eg. `/var/www/deploy/start.sh` or relative to `WEBROOT` eg. `deploy/start.sh`
- `CRON_FILE` - Optional path to a cron file, content of file will be copied to crontab. Path should be an absolute path eg. `/var/www/deploy/cron.txt` or relative to `WEBROOT` eg. `deploy/cron.txt`

Source: [https://github.com/AVONnadozie/docker-webserver](https://github.com/AVONnadozie/docker-webserver)

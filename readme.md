#Docker-PHP7

A quick and easy way to setup your PHP application using Docker and docker-compose. This will setup a developement environment with PHP7-fpm, MariaDB and Nginx.

##Usage
~~~
git clone git@github.com:shameerc/docker-php7.git
cd docker-php7
docker-compose up
~~~

###Structure

~~~
├── app
│   └── public
│       └── index.php
├── database
├── docker-compose.yml
├── fpm
│   ├── Dockerfile
│   └── supervisord.conf
├── nginx
│   ├── Dockerfile
│   └── default.conf
~~~

- `app` is the directory for project files. Our Nginx config is pointing to `app/public`, which can be changed in `nginx/default.conf`
- `database` is where MariDB will store the database files.


###How it works  
**[Read Here](https://blog.shameerc.com/2016/08/my-docker-setup-ubuntu-php7-fpm-nginx-and-mariadb)**

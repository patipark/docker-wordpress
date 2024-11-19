Docker Environment for Wordpress with FPM & Nginx
===

Run Wordpress through Nginx & PHP FPM effortlessly.


### Install
- clone repo via `$ git clone git@github.com:patipark/docker-wordpress.git`. Place files on the host.
- Create `.env` file on root directory and edit your scret info stuff
```bash

####### Port Access #########
WORDPRESS_PORT_HTTP=8001
WORDPRESS_PORT_HTTPS=8443

# WordPress Configuration
WORDPRESS_DEBUG=1
# Root password for your database
# Change this
MYSQL_ROOT_PASSWORD=somestrong_root_password

# Database name, user and password for your wordpress
# Change these
MYSQL_DATABASE=wordpress_db
MYSQL_USER=wordpress_user
MYSQL_PASSWORD=wordpress_password

# Path to store your wordpress files
WP_CONTENT=./wp-content

# Table prefix
WORDPRESS_TABLE_PREFIX=wp_

# Change this
SITE_URL=example.com


```

- Update certificate domain inside `nginx/default.conf`.
- Run following.

```bash
$ docker-compose up -d
```

### Folder Structure
- nginx/      - Nginx configuration.
- wp-content/ - Wordpress volume.

### Docker Volumes 
- wordpress:/var/www/html
- mysql-datavolume:/var/lib/mysql


### License
MIT


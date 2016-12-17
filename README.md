# Setup

if you already have symfony project, copy it's files under `./symfony` directory.

`docker-compose up --build -d`

if you don't have symfony project, follow those steps to install standard edition symfony:

`docker-compose up --build -d`

`bin/composer create-project symfony/framework-standard-edition ../symfony -vvv --prefer-source`

if composer create-project has stopped for some reason you can get into `/var/www/symfony` and continue installation by typing

`bin/composer install -vvv --prefer-source`

Note: This process takes a while, the `-vvv` option is for more verbose output to show what is happening under the hood. The biggest download is the symfony package itself.

Add `symfony.dev` to your hosts files and access your application under `symfony.dev/app_dev.php`

On linux you can use this command `echo $(docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' php) symfony.dev | sudo tee -a /etc/hosts`

Note: If you see "You are not allowed to access this file. Check app_dev.php for more information." just edit `web/app_dev.php` file and remove part that handles access or replace with something more comfortable.

Note: After restart you machine you can run your application suite throught

`docker-compose start`

Explanations
************

`bin/composer` - is an shortcut to execute `composer` command straightforward on container.
 
 This equals to:

`docker-compose exec php composer create-project symfony/framework-standard-edition symfony -vvv --prefer-source`

or

~~~
docker-compose exec php bash
composer create-project symfony/framework-standard-edition symfony
~~~

Note:

If you want you can also call php script on your running container for example.

`bin/php web/app.php`

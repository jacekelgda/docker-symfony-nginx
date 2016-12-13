# Setup

if you already have symfony project, copy it's files under `./symfony` directory.

`docker-compose up --build`

if you don't have symfony project, follow those steps to install standard edition symfony:

`docker-compose up --build`

`docker-compose exec php bash`

`cd /var/www`

`composer create-project symfony/framework-standard-edition symfony -vvv --prefer-source`

if composer create-project has stopped for some reason you can get into `/var/www/symfony` and continue intallation by typing

`composer install -vvv --prefer-source`

Note: This process takes a while, the `-vvv` option is for more verbose output to show what is happening under the hood. The biggest download is the symfony package itself.

Add `symfony.dev` to your hosts files and access your application under `symfony.dev/app_dev.php`

Note: If you see "You are not allowed to access this file. Check app_dev.php for more information." just edit `web/app_dev.php` file and remove part that handles access or replace with something more comfortable.

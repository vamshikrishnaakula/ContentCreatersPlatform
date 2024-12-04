
- Laravel 9
- Bootstrap 4.6.0
- jQuery

#### Requirements

* PHP 8.0.2+
* Mysql / MariaDB (5.7/8.X)
* Apache & mod_rewrite / Nginx
* Node, Composer & at least 2GB of RAM for dev builds

#### Install

````
1) Create db
2) cp .env.sample .env # Edit values, add db
3) composer install
4) php artisan npm:install
6) npm run prod
7) php artisan key:generate
8) php artisan migrate
9) php artisan db:seed
10) php artisan voyager:admin your@email.com # To add new admin user
````
_Note*_ If having issues with composer install, try `php -d memory_limit=1G /usr/bin/composer install`


#### Saving admin state via seeds

_Saving admin panel state. This will remove all prior admin related seeds and reverse genererate new ones - so default admin state & settings will persist._

````
php artisan admin:save
````

_Publishing frontend libraries to public directory. Eg: You npm add a new lib and need to include it  into your views._
```
php artisan npm:publish
```


_Running Code quality checkers and fixers_

````
php artisan code:check php/js cs/pasta
php artisan code:fix php/js
````

_Setting up the crons_

````
* * * * * cd /path-to-your-project && php artisan schedule:run >> /dev/null 2>&1

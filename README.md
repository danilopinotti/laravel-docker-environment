# Laravel Docker Environment
This project is my simple docker environment that I use with Laravel projects.

## Initial considerations
To work properly, this project needs to be root of your project.

This project was developed to work only in Linux systems.

## Setup
- Clone or download this repository in local machine.
- Grant permission to execute `laravel-docker` script:
    - `$> chmod +x ./laravel-docker`
- Put your Laravel project inside `project` folder.
- Done!

## Environment
### Internal manual
First, the laravel-docker has an internal manual. To print it, enter command:
```
$> ./laravel-docker
```

### Up environment
To up the environment, enter command:
```
$> ./laravel-docker start
```
If any service fails to start, the laravel-docker will stop all environment.

### Down environment
To stop the environment, enter command:
```
$> ./laravel-docker stop
```

### Clean environment
To Down the environment, clean orphans and remove network, enter command:
```
$> ./laravel-docker clean
```

## Laravel .env setup
Using this Docker environment, your Laravel project also needs to be properly configured.
To configure, ensure your .env has the following entries:
```
DB_CONNECTION=pgsql
DB_HOST=postgres
DB_PORT=5432
DB_DATABASE=app_dev
DB_USERNAME=postgres
DB_PASSWORD=laraveldocker

REDIS_HOST=redis
REDIS_PASSWORD=null
REDIS_PORT=6379

MAIL_DRIVER=smtp
MAIL_HOST=mailcatcher
MAIL_PORT=1025
MAIL_USERNAME=''
MAIL_PASSWORD=''
MAIL_ENCRYPTION=null
```

## Recommended aliases
Usually developers configure some aliases to speed the development.
Using this environment, I recommend following aliases:
```
# To run "php artisan" inside container writing "pa"
alias pa="docker-compose exec app php artisan"

# To run "composer" inside container writing "dcomposer"
alias dcomposer="docker-compose exec app composer"

# To run "phpunit" inside container writing "dphpunit"
alias dphpunit="docker-compose exec app ./vendor/bin/phpunit"

# To run "npm" inside container writing "dnpm"
alias dnpm="docker-compose exec app npm"
```

## License
The MIT License (MIT).
Please see [License File](LICENSE.md) for more information.
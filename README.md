# TikTok alternative Frontend
Use Tiktok using an alternative frontend, inspired by Nitter.

## Installation
Clone the repository and fetch the requiered external packages with:
```bash
composer install
```

Then you can run it using for example the PHP Development Server with:
```bash
php -S localhost:8080
```

## Configuration
### .env
Move the .env.example file to .env and modify it.

### Apache
If you are using Apache you don't have to do anything more

### Nginx
Add the following to your config (you can modify the tiktok-viewer part if you have or not a subdir):
```
location /tiktok-viewer {
    return 302 $scheme://$host/tiktok-viewer/;
}

location /tiktok-viewer/ {
    try_files $uri $uri/ /tiktok-viewer/index.php?$query_string;
}

location /tiktok-viewer/.env {
    deny all;
    return 404;
}
```

## Known issues
* Right now there is an error when trying to fetch the desired user, there is already a pull request not merged yet fixing this issue on the TikTokApi repo, you can check it out [here](https://github.com/ssovit/TikTok-API-PHP/pull/43)

## TODO
* Allow searching for just one video using the ID
* Code cleanup

## Credits
* [TikTok-API-PHP](https://github.com/ssovit/TikTok-API-PHP)
* [steampixel/simple-php-router](https://github.com/steampixel/simple-php-router)
* [PHP dotenv](https://github.com/vlucas/phpdotenv)
* [Bulma](https://github.com/jgthms/bulma)

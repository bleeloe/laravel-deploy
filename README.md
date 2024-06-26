# laravel-deploy
Guidance to deploy Laravel application on Linux systems. 

## Setting Permission Directory 
Make your user as owner and www-data as as group owner to the laravel's directory and files

set owndership directory and files: 
```bash
sudo chown -R youruser:www-data /var/www/laravel-app-root
```

set directories permission 
```bash
sudo find /var/www/laravel-app-root -type f -exec chmod 775 {} \; 
```

set files permission 
```bash
sudo find /var/www/laravel-app-root -type f -exec chmod 664 {} \; 
```

set persmission storage and cache 
```bash
cd /var/www/laravel-app-root
sudo chgrp -R www-data storage bootstrap/cache
sudo chmod -R ug+rwx storage bootstrap/cache
```
if you have directory for uploads then you need to add same permission like storage and cache 



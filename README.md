
Follow these steps:

1. **first**

   /etc/hosts -> add new -> 127.0.0.1   yourdomain.local

2. ```shell
   /etc/apache2/site-available/ 000-default conf  copy to yourdomain.local.conf	
		<VirtualHost *:80>
  			  ServerName yourdomain.local
			  DocumentRoot /path/to/your/laravel/project/public
			 <Directory /path/to/your/laravel/project/public>
			 Options Indexes FollowSymLinks
			  AllowOverride All
			 Require all granted
			</Directory>
		</VirtualHost>
   ```
3. 
     ```shell
    sudo a2ensite yourdomain.local.conf
    ```
4.
    ```shell
   sudo a2enmod rewrite
    ```

5.
	```shell
	sudo systemctl restart apache2
	```

6. 
	```shell
	APP_URL=http://yourdomain.local
	```

7.
	```shell
	php artisan config:clear
	```


First => /etc/hosts -> add new -> 127.0.0.1   yourdomain.local
Second => /etc/apache2/site-available/ 000-default conf  copy to yourdomain.local.conf	
		<VirtualHost *:80>
  			  ServerName yourdomain.local
			  DocumentRoot /path/to/your/laravel/project/public
			 <Directory /path/to/your/laravel/project/public>
			 Options Indexes FollowSymLinks
			  AllowOverride All
			 Require all granted
			</Directory>
		</VirtualHost>	
Third=> sudo a2ensite yourdomain.local.conf
Fourth =>sudo a2enmod rewrite
Fifth =>sudo systemctl restart apache2
Sisth => APP_URL=http://yourdomain.local
Seventh => php artisan config:clear

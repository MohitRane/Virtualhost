# Virtualhost

-------------
Virtual host
-------------

==> Folder name is almecstaging.local

	sudo cp /etc/apache2/sites-available/000-default.conf /etc/apache2/sites-available/almecstaging.local.conf

	sudo gedit /etc/apache2/sites-available/almecstaging.local.conf

	<VirtualHost *:80>
	    ServerAdmin webmaster@localhost
	    ServerName almecstaging.local
	    ServerAlias www.almecstaging.local
	    DocumentRoot /var/www/html/almecstaging.local/

	    ErrorLog ${APACHE_LOG_DIR}/error.log
	    CustomLog ${APACHE_LOG_DIR}/access.log combined

	    <Directory /var/www/html/almecstaging.local/ >
	            Require all granted
	            AllowOverride All
	            Options Indexes
	    </Directory>
	</VirtualHost>

	# vim: syntax=apache ts=4 sw=4 sts=4 sr noet

==> Make Changes to etc/hosts file,

	127.0.0.1		almecstaging.local
	192.168.0.106	almecstaging.local

==> Enable site config with below commands

	sudo a2ensite pwa-magento.com.conf
	sudo a2ensite 000-default.conf
	sudo service apache2 restart
	sudo service apache2 reload

==> Make changes to core_config_data table as given below screenshot,

	https://nimb.ws/um5DC7

	Note:- Only add ip Address if you're sharing the url in same network.





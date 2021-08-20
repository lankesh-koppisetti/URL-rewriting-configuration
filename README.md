# URL-rewriting-configuration

To allow URL rewriting in your project follow below  steps.

**Create .htaccess file in your project**
`.htaccess` file allow us to command apache server 


**Install and enable rewrite module of apache**
sudo a2enmod rewrite

**Properly configure the apache configuration files**
Go inside /var/apache2/sites-enabled and edit 000-default.conf 
and add below lines inside <VirtualHost *:80> </VirtualHost>

<Directory /var/www/html/your_project_folder>
     Options Indexes FollowSymLinks
     AllowOverride All ----> this line is important
     Require all granted  
     Order allow,deny
    allow from all
</Directory>

**finally restart your apacheserver**
sudo systemctl restart apache2

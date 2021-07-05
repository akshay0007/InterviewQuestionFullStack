<VirtualHost *:8084>

        DocumentRoot /home/vipin/project/vatsystem/dist/dashboard
 
 </VirtualHost>
 

    cd /etc/apache2
 
    
sudo vi ports.conf

    <Directory /home/ubuntu/project/expat-taxation-web/dist/dashboard/>
        Options Indexes FollowSymLinks
        AllowOverride All
        Require all granted
</Directory>
 
    sudo vi /etc/apache2/sites-enabled/000-default.conf


<VirtualHost *:80>

        DocumentRoot /home/ubuntu/project/expat-taxation-web/dist/dashboard
 

</VirtualHost>
 
 
    sudo service apache2 restart

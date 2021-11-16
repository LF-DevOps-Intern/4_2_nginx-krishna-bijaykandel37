The used commands for QN1 are:

To install nginx: 
==> Sudo apt-get install nginx

To allow Nginx services are to be allowed in the firewall.
==> Ufw allow ‘Nginx Full’
==> Ufw allow ‘Nginx HTTP’

To check Nginx status:
==> Sudo systemctl status nginx

To copy our application  to /var/www/html/:
==> Cp NginxTask/ /var/www/html/

To change ownership to nonroot user:
==> Sudo chown -R $USER:$USER /var/www/html/NginxTask/

Now we create a configuration file for the application which is to be deployed:
==> Cp default NginxTask.conf

To edit the file:
==> Nano NginxTask.conf
Inside this file some configurations are edited:

To edit the nginx.conf file:
==> Nano /etc/nginx/nginx.conf
Inside http block, a Server block is added with some configurations as shown:

To create symlink between sites-enabled and sites-available:
==> ln -s /etc/nginx/sites-available/NginxTask.conf /etc/nginx/sites-enabled/

To list host:
==> Sudo nano /etc/hosts

To test the system configurations, 
==> nginx -t

To restart Nginx:
==> Sudo systemctl restart nginx

And we can go to the domain to see the results.

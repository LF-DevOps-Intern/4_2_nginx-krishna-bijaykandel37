QN3. Nginx Reverse proxy all http requests to nodes js api.

Firstly, a reverse_proxy.conf file is created in /sites-available/ directory:
==> Nano reverse_proxy.conf


Then a symlink is created using command:
==> Ln -rs /etc/nginx/sites-available/reverse_proxy.conf /etc/nginx/sites-enabled

Now the config is tested using command ==> nginx -t, and restarted nginx using:
==> Systemctl restart nginx

Now node app is started using pm2:
==> Pm2 start index.js


We can verify by running the app in browser.
If we enter the domain of nginx server with port 81, we can see the same node app.

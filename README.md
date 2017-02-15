murrayfamily-site
==============

# install

## git instructions

```
sudo rm -rf murrayfamily-site /var/www/themurrayfamily-ssl
```

### git url

```
eval $(ssh-agent -s); ssh-add .ssh/github_rsa
git clone git@github.com:chris18890/murrayfamily-site.git
sudo cp -r murrayfamily-site/themurrayfamily/ /var/www/themurrayfamily-ssl; sudo chown www-data -R /var/www
```

# Setup - multiple domains/ssl sites

```
nano murrayfamily-site/themurrayfamily-ssl.conf
sudo cp murrayfamily-site/themurrayfamily-ssl.conf /etc/apache2/sites-available/themurrayfamily-ssl.conf; sudo a2ensite themurrayfamily-ssl; sudo service apache2 restart
sudo certbot --apache -d themurrayfamily.me.uk -d www.themurrayfamily.me.uk --agree-tos --renew-by-default --no-redirect
```

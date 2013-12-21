## How it worked
* The example host in this example is :http://django.test (you can append *127.0.0.1 django.test* in /etc/hosts)
* Create nginx configuration file which point to socket where uwsgi is listening
ln -s link : sudo ln -s /your_path/django_nginx.conf /etc/nginx/sites-enabled
* Restart nginx : *sudo service nginx restart *
After this step you can check nginx worked correctly or not by visit http://django.test/static/style.css. if browse return the content of this file, that indicate nginx loaded your configuration file succesfully otherwise check the log file at /var/log/nginx/error.
* Run uwsgi by cd to django_nginx and run *uwsgi --ini uwsgi.ini* to listen the request from nginx
* Check the result on http://django.test and hello page appear.
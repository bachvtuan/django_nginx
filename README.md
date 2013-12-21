# Stratch django app worked with nginx by using uwsgi middleware
## How it worked
* The example host in this example is :http://django.test (you can append *127.0.0.1 django.test* in /etc/hosts)
* Create nginx configuration file which point to socket where uwsgi is listening
ln -s link : sudo ln -s /your_path/django_app.conf /etc/nginx/sites-enabled
* Restart nginx : *sudo service nginx restart *
After this step we can check nginx is working or not by visit http://django.test/static/style.css. if browse return the content of this file, that indicate nginx loaded your configuration file succesfully other check the log file at /var/log/nginx/error.
* Run uwsgi by cd to django_app and run *uwsgi --ini uwsgi.ini*
* Check the result on http://django.test and Django'shello page appear.
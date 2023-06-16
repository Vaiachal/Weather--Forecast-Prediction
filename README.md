# Weather--Forecast-Prediction
A website that used to illustrate the weather forecast prediction using different Machine learning algorithms.and tools.

* Features
* Cookie usage when user logs in
* Database for user login credentials
* Login and signup page
* Flask web server for ubntu
* naive bias classifier.
* Random Forest Classifier model that takes user's inputs and predicts weather

CONFIGURATION:
Nginix:
server {
        listen 80;

        location / {
                proxy_pass http://127.0.0.1:8000;
                proxy_set_header Host $host;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }
}

sudo unlink /etc/nginx/sites-enabled/default
sudo nginx -t

2) Gunicorn Config:
   [Unit]
Description=Flask App

[Service]
Type=simple
ExecStart=/usr/bin/gunicorn3 --chdir /var/www/html/ app:app

[Install]
WantedBy=multi-user.target
Then start and check the service:
sudo systemctl start weather-prediction
sudo systemctl status weather-prediction

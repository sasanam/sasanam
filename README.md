Get your server up to date:

apt update && apt upgrade -y

Also install curl and socat:


apt install curl socat -y

Install Acme Script

Download and install the Acme script for getting a free SSL certificate:


curl https://get.acme.sh | sh

Get Free SSL Certificate

Set the default provider to Let’s Encrypt:


~/.acme.sh/acme.sh --set-default-ca --server letsencrypt

Register your account for a free SSL certificate. In the next command, replace xxxx@xxxx.com by your actual email address:


~/.acme.sh/acme.sh --register-account -m xxxx@xxxx.com

Obtain an SSL certificate. In the next command, replace host.mydomain.com by your actual host name:


~/.acme.sh/acme.sh --issue -d host.mydomain.com --standalone

After a minute or so, the script terminates. On success, you will receive feedback as to the location of the certificate and key:


Your cert is in: /root/.acme.sh/host.mydomain.com/host.mydomain.com.cer

Your cert key is in: /root/.acme.sh/host.mydomain.com/host.mydomain.com.key

The intermediate CA cert is in: /root/.acme.sh/host.mydomain.com/ca.cer

And the full chain certs is there: /root/.acme.sh/host.mydomain.com/fullchain.cer

You cannot use the certificate and key in their current locations, as these may be temporary. Therefore install the certificate and key to a permanent location. In the next command, replace host.mydomain.com by your actual host name:


~/.acme.sh/acme.sh --installcert -d host.mydomain.com --key-file /root/private.key --fullchain-file /root/cert.crt

Install certificate and key issued by Acme script


Run the X-UI Install Script

Download and run the one-click install script provided by the developer:


bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)


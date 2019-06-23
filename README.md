# NginX-ssl-instalaltion

```console
cd /etc/ssl <!--- папката със сертификатите -->
ls
cd certs
ls
cd ..
cd private/
su
sudo su
exit
sudo su
exit
ls
sudo ls
ls
sudo su
exit
sudo su
exit
sudo su
exit
sudo su
exit
pws
pwd
ls
exit
cd /etc/nginx/sites-
cd /etc/nginx/sites-enabled/
ls
nano EXAMPLE.COM
cd /etc/certs
cd /etc/ssl/certs
ls
openssl x509 -noout -in need.crt 
openssl x509 -noout -text -in need.crt 
cd ~/
openssl req -new -newkey rsa:2048 -nodes -keyout EXAMPLE_YEAR.key -out EXAMPLE_YEAR.csr
ls
less EXAMPLE_YEAR.csr 
ls
cat www_EXAMPLE_COM.crt www_EXAMPLE_COM.ca-bundle 
cat www_EXAMPLE_COM.crt www_EXAMPLE_COM.ca-bundle >> EXAMPLE_YEAR.crt
nano EXAMPLE_YEAR.crt 
cd /etc/ssl
ls
less /etc/nginx/sites-enabled/EXAMPLE.COM 
cd ~/
sudo su
ls
rm EXAMPLE_YEAR.key
exit
exit
```
https://www.namecheap.com/support/knowledgebase/article.aspx/467/67/how-to-generate-csr-certificate-signing-request-code

https://www.namecheap.com/support/knowledgebase/article.aspx/795/14/how-to-install-ssl-certificates

https://www.namecheap.com/support/knowledgebase/article.aspx/795/69/how-to-install-ssl-certificates

https://www.namecheap.com/support/knowledgebase/article.aspx/9423/33/installing-a-ssl-certificate-on-apache

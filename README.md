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
nano``` **_EXAMPLE.COM-** 
```console
cd /etc/certs
cd /etc/ssl/certs
ls
openssl x509 -noout -in need.crt 
openssl x509 -noout -text -in need.crt 
cd ~/
openssl req -new -newkey rsa:2048 -nodes -keyout need_new.key -out need_new.csr
ls
less need_new.csr 
ls
cat www_needhampoulier_co_uk.crt www_needhampoulier_co_uk.ca-bundle 
cat www_needhampoulier_co_uk.crt www_needhampoulier_co_uk.ca-bundle >> need_new.crt
nano need_new.crt 
cd /etc/ssl
ls
less /etc/nginx/sites-enabled/needhampoulier.co.uk 
cd ~/
sudo su
ls
rm need_new.key
exit
exit
```
https://www.namecheap.com/support/knowledgebase/article.aspx/467/67/how-to-generate-csr-certificate-signing-request-code

https://www.namecheap.com/support/knowledgebase/article.aspx/795/14/how-to-install-ssl-certificates

https://www.namecheap.com/support/knowledgebase/article.aspx/795/69/how-to-install-ssl-certificates

https://www.namecheap.com/support/knowledgebase/article.aspx/9423/33/installing-a-ssl-certificate-on-apache

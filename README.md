# NginX-ssl-instalaltion

```console
cd /etc/ssl
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
nano needhampoulier.co.uk 
   44  cd /etc/certs
   45  cd /etc/ssl/certs
   46  ls
   47  openssl x509 -noout -in need.crt 
   48  openssl x509 -noout -text -in need.crt 
   49  cd ~/
   50  openssl req -new -newkey rsa:2048 -nodes -keyout need_new.key -out need_new.csr
   51  ls
   52  less need_new.csr 
   53  ls
   54  cat www_needhampoulier_co_uk.crt www_needhampoulier_co_uk.ca-bundle 
   55  cat www_needhampoulier_co_uk.crt www_needhampoulier_co_uk.ca-bundle >> need_new.crt
   56  nano need_new.crt 
   57  cd /etc/ssl
   58  ls
   59  less /etc/nginx/sites-enabled/needhampoulier.co.uk 
   60  cd ~/
   61  sudo su
   62  ls
   63  rm need_new.key

https://www.namecheap.com/support/knowledgebase/article.aspx/467/67/how-to-generate-csr-certificate-signing-request-code

https://www.namecheap.com/support/knowledgebase/article.aspx/795/14/how-to-install-ssl-certificates

https://www.namecheap.com/support/knowledgebase/article.aspx/795/69/how-to-install-ssl-certificates

https://www.namecheap.com/support/knowledgebase/article.aspx/9423/33/installing-a-ssl-certificate-on-apache

```

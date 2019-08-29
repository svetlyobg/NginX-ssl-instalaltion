# ssl


CHECK current config
```console
less /etc/nginx/sites-enabled/tab.example.co.uk
```

```to do - show configuration```

Find certificates location
>/etc/ssl/tab.example.co.uk/

Go to home dir and generate ceritificate request(CSR) and private key
>cd ~/  
>openssl req -new -newkey rsa:2048 -nodes -keyout tab_example_2019.key -out tab_example_2019.csr

Check and copy CSR INTO NAMECHEAP
>cat tab_example_2019.csr
```
-----BEGIN CERTIFICATE REQUEST-----
MIIC5jCCAc4CAQAwgaAxCzAJBgNVBAYTAkdCMQ8wDQYDVQQIDAZMb25kb24xDzAN
BgNVBAcMBkxvbmRvbjEhMB8GA1UECgwYSW50ZXJuZXQgV2lkZ2l0cyBQdHkgTHRk
MSEwHwYDVQQDDBh0YWIubmVlZGhhbXBvdWxpZXIuY28udWsxKTAnBgkqhkiG9w0B
....
....
511icaIWvFZlMVcz+KuIAFkwrAesEFgci+tulLfnT4w7Kwcf+fhQaHFpdWgnhXXY
+lssQJxsGiBkkYd+3BQcexqtW/ZEi5eEe5p6JF8J7Jd86tyywj4L2EINdeV3Iq6H
X8hjNusDPZr74VDU80YuWMFjVaqCX6XfG9Jl1vKoUVwsHAr3ocKpbhsbDt0vV+pp
mK0SNYQbgVpcIjJ5mImlrFs8V3kv3oEQfzE=
-----END CERTIFICATE REQUEST-----
```

UPLOAD THE BUNDLE AND .CRT TO THE HOME DIRECTORY (/home/user/) ( filezilla, scp,).
*BUNDLE - your certificate* and the certificates of the issuer (certificate chain). The certificate contains the public key.

Go to folder with current certificates
>cd /etc/ssl/tab.example.co.uk/  
>ls

RENAME THE OLD PEM JUST IN CASE FOR BACKUP
>sudo cp key key.2019.old   
>sudo cp pem pem.2019.old  

Concat the certificate and the certificates of the issuer (certificate chain) 
> cd ~/  
> cat 2019_tab_example_co_uk.crt 2019_tab_example_co_uk.ca-bundle >> pem  
> cd /etc/ssl/cd tab.example.co.uk/  
> cd ~/  

MOVE THE PEM TO THE SSL FOLDER
>sudo mv pem /etc/ssl/tab.example.co.uk/
MOVE THE KEY TO THE SSL FOLDER
>sudo mv tab_example_2019.key /etc/ssl/tab.example.co.uk/key 

CHANGE THE KEY PERMISSIONS TO READ-ONLY
>sudo chmod 400 key

Check if ... – – – BEGIN AND – – – END – CERTIFICATE LINES ARE CORRECTLY WRITTEN
>less pem

Edit pem
>nano pem  

Restart the web server
>sudo service nginx restart

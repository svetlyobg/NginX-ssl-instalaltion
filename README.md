# SSL Instalaltion On NginX

***
# How to Install/Renew Nginx/Ubuntu SSL Certificate 

### 1. Request CSR
```console
openssl req -new -newkey rsa:2048 -nodes -keyout  DOMAIN.key -out DOMAIN.csr
```
### 2. Open, Copy and Paste the CSR Into the CA
```console
cat DOMAIN.csr
```
-----BEGIN CERTIFICATE REQUEST-----
MIIC5jCCAc4CAQAwgaAxCzAJBgNVBAYTAkdCMQ8wDQYDVQQIDAZMb25kb24xDzAN
***
***
***
mK0SNYQbgVpcIjJ5mImlrFs8V3kv3oEQfzE=

-----END CERTIFICATE REQUEST-----

### 4. Somehow Validate the CSR

### 5. Somehow Upload Both .ca-bundle and .crt to the Server

### 6. Backup the Previous .key and pem files
```console
cd /etc/ssl/WEBSITE-DIRECTORY/
sudo cp DOMAINKEY DOMAINKEY.old
sudo cp DOMAINPEM DOMAINPEM.old
sudo cp DOMAINCRT DOMAINCRT.old
sudo cp DOMAINBUNDLE DOMAIN.old
```
### 7. Create a New pem File
```console
cd ~/
cat DOMAIN.crt DOMAIN.ca-bundle >> pem
```
### 8. Check if the – – – BEGIN AND – – – END – Certificate Lines are Correctly Written
```console
less pem
```
### 9. Change The .key Permissions To Read-Only
```console
sudo chmod 400 key
```
### 10. Move Both the New pem and the New key Files to the SSL Directory
```console
sudo mv pem /etc/ssl/WEBSITE-DIRECTORY/
sudo mv DOMAIN.key /etc/ssl/WEBSITE-DIRECTORY/key
```
### 11. Restart the Nginx Service
```console
sudo service nginx restart
```
***

1. Check current configuration
```console
less /etc/nginx/sites-enabled/tab.example.co.uk
```
2. Show configuration
```console
to do - show configuration
```

3. Find certificates location
```console
/etc/ssl/tab.example.co.uk/
```

4. Go to home dir and generate ceritificate request(CSR) and private key
```console
cd ~/
```
```console
openssl req -new -newkey rsa:2048 -nodes -keyout tab_example_2019.key -out tab_example_2019.csr
```

5. Check and copy CSR into Namecheap

```console
cat tab_example_2019.csr
```
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

Choose - **Any other service - (cPanel, Apache, NGINX)** and then confirm the domain by **email verification** (the SSL will be emailed).

6. Upload the bundle and .crt to the home directory (/home/user/*website*) ( filezilla, scp,).
*BUNDLE - your certificate* and the certificates of the issuer (certificate chain). The certificate contains the public key. Verify it 

7. Go to folder with current certificates
```console
cd /etc/ssl/tab.example.co.uk/
ls
```

8. Rename the old pem just in case for backup
```console
sudo cp key key.2019.old
sudo cp pem pem.2019.old
sudo cp crt crt.2019.old
sudo cp bundle bundle.2019.old
```

9. Concat the certificate and the certificates of the issuer (certificate chain) 
```console
cd ~/
cat 2019_tab_example_co_uk.crt 2019_tab_example_co_uk.ca-bundle >> pem
cd /etc/ssl/cd tab.example.co.uk/
cd ~/
```

10. Move the pem to the SSL folder
```console
sudo mv pem /etc/ssl/tab.example.co.uk/
```

11. Move the key to the SSL folder
```console
sudo mv tab_example_2019.key /etc/ssl/tab.example.co.uk/key
```

12. Change the key permissions to read-only
```console
sudo chmod 400 key
```

13. Check if ... – – – BEGIN AND – – – END – Certificate lines are correctly written
```console
less pem
```

14. Edit pem
```console
nano pem
```

15. Restart the web server
```console
sudo service nginx restart
```

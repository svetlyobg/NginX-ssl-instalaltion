# SSSL Instalaltion On NginX


1. Check current configuration
```console
less /etc/nginx/sites-enabled/tab.example.co.uk
```
1. Show configuration
```console
to do - show configuration
```

1. Find certificates location
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

6. Upload the bundle and .crt to the home directory (/home/user/) ( filezilla, scp,).
*BUNDLE - your certificate* and the certificates of the issuer (certificate chain). The certificate contains the public key.

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
sudo mv pevm /etc/ssl/tab.example.co.uk/
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

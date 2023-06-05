#Generate rsa private key which we can use for csr and cert signing later

openssl genrsa -aes256 -out private.key 2048

#Generate rsa private key with specified algo and passphrase

openssl genrsa -aes256 -passout pass:manas -out keypair.key 2048

# we can extract the public key from this private key too

openssl-certs % openssl rsa -in private.key -pubout -out public.key

#create csr 

openssl req -new -key private.key -out newcsrname.csr

#sign cert
openssl x509 -req -days 360 -in csr.csr -signkey private.key -out newcert.crt

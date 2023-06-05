#Generate rsa private key which we can use for csr and cert signing later

openssl genrsa -aes256 -out private.key 2048

#Generate rsa private key with specified algo and passphrase

openssl genrsa -aes256 -passout pass:manas -out keypair.key 2048

# we can extract the public key from this private key too

openssl-certs % openssl rsa -in private.key -pubout -out public.key

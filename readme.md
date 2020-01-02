openssl genrsa -aes256 -passout pass:x -out keypair.key 2048
openssl rsa -passin pass:x -in keypair.key -out $(hostname).key
openssl req -new -key $(hostname).key -out $(hostname).csr
openssl x509 -req -days 3650 -in $(hostname).csr -signkey $(hostname).key -out $(hostname).crt

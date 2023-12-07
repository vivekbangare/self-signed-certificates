# Generate Self-Signed Certificate

Open a terminal and run the following commands:

```
# Generate private key and certificate signing request
openssl req -newkey rsa:2048 -nodes -keyout key.pem -out csr.pem

# Generate the self-signed certificate using the private key and signing request
openssl x509 -req -days 365 -in csr.pem -signkey key.pem -out cert.pem

# Combine the private key and certificate into a single PEM file
cat key.pem cert.pem > certificate.pem

# (Optional) Verify the contents of the generated certificate
openssl x509 -in certificate.pem -text -noout

```
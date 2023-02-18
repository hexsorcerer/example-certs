# [OpenSSL](https://www.openssl.org/docs/man1.1.1/man1/)
This is the primary tool used to manage certificates and keys. Most of the other

This is the type of certificate that's used for HTTPS.

[X.509 on Wikipedia](https://en.wikipedia.org/wiki/X.509)

In order to make one of these, you have to send a [Certificate signing request](https://en.wikipedia.org/wiki/Certificate_signing_request) to a certificate authority. In the case of generating your own certificates, that authority will be the openssl application.

The command to do so is:
```
openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 -nodes -keyout example.key -out example.crt -subj "/CN=example.com" -addext "subjectAltName=DNS:example.com,DNS:www.example.net,IP:10.0.0.1"
```

Let's break it down:

## [req](https://www.openssl.org/docs/man1.1.1/man1/req.html)
Creates the PKCS#10 certificate request needed to generate the certificate.

## -x509
Tells ```openssl``` to create a self-signed certificate instead of the PKCS#10 request.

## -newkey rsa:4096 -sha256
Creates a new certificate request and a new RSA private key. The SHA256 is used for the digital signature.

## -days 3650
The lifetime of the certificate.

## -nodes
Says to not encrypt the private key that's generated.

## -keyout example.key
Specifies the output file for the private key.

## -out example.crt
Specifies the output file for the certificate.

## -subj "/CN=example.com"
Sets the subject name for the request.

CN is Common Name, and is the fully qualified domain name of the site. This is one of several Distinguished Names (DN), you can see the rest on [the wikipedia site](https://en.wikipedia.org/wiki/Certificate_signing_request#Procedure).

## -addext "subjectAltName=DNS:example.com,DNS:www.example.net,IP:10.0.0.1"
-addext lets you add an extension to the certificate (if it's X.509).

subjectAltName (SAN) is an extension to the X.509 standard that lets you secure multiple domain names with a single certificate. Check out this [DigiCert FAQ](https://www.digicert.com/support/resources/faq/public-trust-and-certificates/what-is-a-multi-domain-san-certificate) for more info.
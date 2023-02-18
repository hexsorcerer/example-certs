# mkcert
This is a tool designed to make it fast and easy to generate certificates that are signed and trusted, which avoids some of the problems associated with self-signed certificates.

First you need to install ```mkcert``` in the trusted store:
```
mkcert --install
```
This will install a root CA under the ```Trusted Root Certificate Authorities``` store, which you can see with ```certmgr```.

Once you've done that, you can then generate your own signed and trusted certs:

```
mkcert -key-file example.key -cert-file example.crt example.org
```
Since you have ```mkcert``` in the trusted store from the previous step, this cert will be trusted and not generate any errors in the browser.

## [PFX](https://en.wikipedia.org/wiki/PKCS_12)
PFX is an older standard that allows the bundling of a private key and a certificate in a single file. These used to still be used in Visual Studio and some other Microsoft products, but .NET 5 has added support for ```PEM``` formatted certs so you may not need this.

However, if you do need it for whatever reason:
```
mkcert -pkcs12 -p12-file example.pfx example.org
```

Verify with:
```
certutil -dump ./example.pfx
```

Password is ```changeit```.
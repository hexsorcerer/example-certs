# [dotnet dev-certs](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-dev-certs)

Yet another tool available to help you generate certs is good ol' dotnet CLI.
```
dotnet dev-certs https --export-path ./example.crt --no-password  --format PEM
```

This will do much the same as ```mkcert``` in that it will generate a .crt and .key file for you.

## What about PFX?
PFX is an older standard that allows bundling of private keys and certificates together in a single file. It's been lingering around in Microsoft tools but in .NET 5 they added support for PEM format certs in Kestrel so I'm not sure if there's much of a need to worry about it anymore.

Anyways, you can create a PFX with this tool also, if you need it for some reason:
```
dotnet dev-certs https --export-path ./example.pfx --password changeit
```
You can verify this file using certutils:
```
certutils -dump ./example.pfx
```
Which should prompt you for the password, and then show you something like this:
```
================ Certificate 0 ================
================ Begin Nesting Level 1 ================
Element 0:
Serial Number: 63284dd039e22cc1
Issuer: CN=localhost
 NotBefore: 8/20/2022 8:25 PM
 NotAfter: 8/20/2023 8:25 PM
Subject: CN=localhost
Signature matches Public Key
Root Certificate: Subject matches Issuer
Cert Hash(sha1): 15e7c744fa1c8a17eeccfc51d30624d8afa0934e
----------------  End Nesting Level 1  ----------------
  Provider = Microsoft Software Key Storage Provider
Private key is NOT plain text exportable
Encryption test passed
CertUtil: -dump command completed successfully.
```
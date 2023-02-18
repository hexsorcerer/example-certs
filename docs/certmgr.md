# [certmgr](https://learn.microsoft.com/en-us/dotnet/framework/tools/certmgr-exe-certificate-manager-tool)

This is a tool to manage your certificate store on Windows machines. Helpful to see what certs are installed, and to remove them if you need to.

There are several stores available and it's not immediately clear which ones matter. Here are the 3 main ones:

## Trusted Root Certification Authorities
Implicitly trusted CAs. Includes all of the certificates in the Third-Party Root CAs store plus root certificates from your organization and Microsoft.

If you used ```mkcert``` to install your own CA, you'll see it here.

## Third-party Root Certification Authorities
Trusted root certificates from CAs other than Microsoft and your organization.

## Personal
Certificates associated with private keys to which you have access. These are the certificates that have been issued to you, or to the computer or service for which you’re managing certificates.


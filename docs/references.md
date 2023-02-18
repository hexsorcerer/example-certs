# References
[Configuring HTTPS in ASP.NET Core across different platforms](https://devblogs.microsoft.com/dotnet/configuring-https-in-asp-net-core-across-different-platforms/)

A nice overview of working with encryption in the .NET world.

[[EPIC]: HTTPS and Certificate Handling in Kestrel #21512](https://github.com/dotnet/aspnetcore/issues/21512)

Shows that PEM support was added to Kestrel in .NET 5.

[How to Manage Certificates using the Microsoft Management Console](https://youtu.be/4mAOUmv1gp4)

One of the only videos on Youtube explaining the important aspects of the ```certmgr``` console on Windows.

[Certificates](https://learn.microsoft.com/en-us/previous-versions/tn-archive/cc700805(v=technet.10))

A dated but excellent detailed explanation of certificates in Windows. Also contains a table defining all of the certificates stores in ```certmgr```.

[mkcert](https://github.com/FiloSottile/mkcert)

Excellent tool that makes it easy to generated trusted signed certs for yourself.

[Manage Certs with Windows Certificate Manager and PowerShell](https://adamtheautomator.com/windows-certificate-manager/)

Another good tutorial with some additional explanation not seen in some of the other ones, like registry keys for the certificate stores.

[It should be mentionned somewhere that p12 password is "changeit" #86](https://github.com/FiloSottile/mkcert/issues/86)

A small but important detail.

[How to use HTTPS for local development](https://web.dev/how-to-use-local-https/)

Excellent guide on doing this, from a dev's point of view.

[What is a Multi-Domain (SAN) Certificate?](https://www.digicert.com/support/resources/faq/public-trust-and-certificates/what-is-a-multi-domain-san-certificate)

Good explanation of SAN, which is used in the ```openssl``` example.

[Subject Alternative Name](https://en.wikipedia.org/wiki/Subject_Alternative_Name)

Good ol' wikipedia.

[Certificate signing request](https://en.wikipedia.org/wiki/Certificate_signing_request)

Has a nice table of all the DNs available to use when generating a request.

[OpenSSL command](https://www.openssl.org/docs/man1.1.1/man1/)

The man pages for all the different ```openssl``` commands.

[How to generate a self-signed SSL certificate using OpenSSL? [closed]](https://stackoverflow.com/a/10176685)

Shows how to use ```openssl``` to generate both the private key and cert in a single command.

[Generate the ASP.NET Core web API certificate](https://github.com/hexsorcerer/example-proxy-envoy/blob/main/docs/certs.md)

My own notes from the last time I worked with certs during the Envoy example project.


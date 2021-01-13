Lifted from:
https://github.com/jsha/minica


Added -roles option

minica -domains localhost -roles "spinn1%0Aspin2%0Aadmin"

check with 

openssl x509 -in cert.pem -text -noout

        X509v3 extensions:
            X509v3 Key Usage: critical
                Digital Signature, Key Encipherment
            X509v3 Extended Key Usage: 
                TLS Web Server Authentication, TLS Web Client Authentication
            X509v3 Basic Constraints: critical
                CA:FALSE
            X509v3 Authority Key Identifier: 
                keyid:91:CB:EE:37:32:22:2C:F5:16:BE:38:EF:ED:A4:0E:49:00:24:BF:B5

            X509v3 Subject Alternative Name: 
                DNS:localhost
            1.2.840.10070.8.1: 
                spinn1%0Aspin2%0Aadmin


# Installation

First, install the [Go tools](https://golang.org/dl/) and set up your `$GOPATH`.
Then, run:

`go get github.com/jsha/minica`

When using Go 1.11 or newer you don't need a $GOPATH and can instead do the
following:

```
cd /ANY/PATH
git clone https://github.com/jsha/minica.git
go build
## or
# go install
```

# Example usage

```
# Generate a root key and cert in minica-key.pem, and minica.pem, then
# generate and sign an end-entity key and cert, storing them in ./foo.com/
$ minica --domains foo.com
```

# Creating https server running on nodejs

### Requirement

- node.js


## Installation

#### Cloning repository and installing dependencies

```bash
$ git clone git@github.com:athlonUA/nodejsHttpsServer.git
$ cd nodejsHttpsServer
$ npm install
```

#### Creating 'self-signed certificate'
There are two kinds of certificates: signed by a 'Certificate Authority' and 'self-signed certificates'. A Certificate Authority is a trusted source for an SSL certificate. Using a certificate from a CA allows your users to be trust the identity of your website.

```bash
$ openssl genrsa -out client-key.pem 2048
$ openssl req -new -key client-key.pem -out client.csr
$ openssl x509 -req -in client.csr -signkey client-key.pem -out client-cert.pem
$ rm client.csr
```

#### Running server

```bash
$ node server.js
$ curl https://localhost:8080
```


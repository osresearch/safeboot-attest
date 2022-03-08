# safeboot-attest server

This is the server side of the safeboot TPM2 attestation protocol.
It can use more full-featured tools, like Python and flask, to serve
the data.

For modularity, the server is split into two pieces:

* `attest-server`, a Flask application that receives the HTTP `POST` requests
and verifies that the quote and eventlog are well-formed. If so it invokes
* `attest-verify`, a user-provided tool that provides the secret to be sealed for the client.


## Installation

```
pip3 install -r requirements.txt
```



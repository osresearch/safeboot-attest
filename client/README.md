# safeboot-attest client

This is as minimal a shell script as possible, since it needs to run
inside of an initrd with very few resources.  The only function supported
is to generate a signed quote over all the PCRs and send it to the
remote attestation server.

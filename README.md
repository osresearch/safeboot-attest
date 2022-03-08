# safeboot's TPM2 remote attestation

This is a simple TPM2 remote attestation framework built for use
with [safeboot](https://safeboot.dev/) and [safeboot-efi](https://github.com/osresearch/uefiblockdev).  The protocol is described in [safeboot.dev/attestation](https://safeboot.dev/attestation).

The client is a shell script that wraps the [tpm2-tools](https://github.com/tpm2-software/tpm2-tools)
to generate ephemeral keys that sign the quote over all PCRs and uses `curl`
to post them to the server, along with the TPM eventlog.

The server is a Python flask application that verifies the quote and
the eventlog are consistent, and that the signature matches.  It shells
out to a user provided program to then validate that the quote is
acceptable, and if so, returns the data that will be sent to the
attesting client.

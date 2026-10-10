# Security

Please do not publish suspected vulnerabilities in a public issue. Use this
repository's **Security → Report a vulnerability** form, which sends a private
report to the Lotus maintainers.

Official releases include SHA-256 checksums and a detached Ed25519 signature.
A build whose hash is not in a validly signed `SHA256SUMS.txt` is not a Lotus
release. The Windows installer is not Authenticode-signed; it is authenticated
by the signed checksum list instead.

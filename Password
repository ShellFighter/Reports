## Issue related to the handling of passwords

While intercepting the traffic with my burp, I noticed that my password is being encoded using Base64 rather than using secure hashing or encryption methods.

## Example of Finding:

In the HTTP request headers, the Authorization header contained Base64-encoded credentials which reveals that passwords are being transmitted or stored in a format that is easily reversible.

## Security Implications

# Reversible Encoding:

Base64 encoding is not a secure method for protecting passwords. It can be easily decoded to reveal the original content, making it vulnerable to unauthorized access.

# Potential Risks:

1- Exposure of Sensitive Information: If Base64-encoded passwords are intercepted or accessed, they can be decoded and misused.

2- Compliance Issues: The use of weak encoding methods may violate industry standards and regulations related to data security.

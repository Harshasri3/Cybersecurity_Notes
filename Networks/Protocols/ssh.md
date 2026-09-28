## 🔐 SSH (Secure Shell Protocol)

SSH is a cryptographic network protocol used to securely access and manage remote systems over an unsecured network. It encrypts communication to protect credentials, commands, and transmitted data from interception.

### Key Features

* **Secure Remote Access** – Log in to remote servers and execute commands securely.
* **Encryption** – Protects network traffic from eavesdropping and interception.
* **Authentication** – Supports password, public-key, keyboard-interactive, and GSSAPI authentication.
* **Public-Key Authentication** – Uses a public/private key pair for secure, passwordless authentication.
* **File Transfer** – Supports secure file transfer through **SCP** and **SFTP**.
* **Port Forwarding & Tunneling** – Securely forwards TCP connections and tunnels traffic.
* **X11 Forwarding** – Allows remote graphical applications to be accessed securely.
* **SOCKS Proxying** – Can route web traffic through an encrypted SSH connection.
* **Server Management** – Commonly used for remote administration, monitoring, and automation.
* **Git Integration** – SSH can be used to securely authenticate with Git repositories.

### Default Port

| Protocol | Transport | Default Port |
| -------- | --------- | -----------: |
| SSH      | TCP       |       **22** |

### SSH Architecture

SSH consists of three major layers:

1. **Transport Layer**

   * Performs key exchange and server authentication.
   * Provides encryption, compression, and integrity protection.

2. **User Authentication Layer**

   * Authenticates the client/user.
   * Supports password, public-key, keyboard-interactive, and GSSAPI methods.

3. **Connection Layer**

   * Multiplexes multiple logical channels over one SSH connection.
   * Supports shell sessions, command execution, and port forwarding.

### Common SSH Algorithms

* **Public Key:** RSA, ECDSA, EdDSA
* **Key Exchange:** Diffie-Hellman, ECDH
* **Integrity/MAC:** HMAC, UMAC, AEAD
* **Encryption:** AES, AES-GCM, ChaCha20-Poly1305
* **Hashing/Fingerprints:** SHA

### SSH Key Management

SSH key-based authentication uses a public/private key pair:

* **Private key** → kept securely on the client.
* **Public key** → stored on the remote server, commonly in `~/.ssh/authorized_keys`.
* `ssh-keygen` → generates SSH key pairs.
* The private key can be protected with a passphrase.
* Unknown server public keys should be verified before accepting them to reduce the risk of impersonation or man-in-the-middle attacks.

### Common Commands

```bash
# Connect to a remote server
ssh username@server_ip

# Connect using a specific private key
ssh -i ~/.ssh/id_rsa username@server_ip

# Generate an SSH key pair
ssh-keygen

# Copy a file to a remote server
scp file.txt username@server_ip:/path/

# Copy a file from a remote server
scp username@server_ip:/path/file.txt .

# Secure file transfer
sftp username@server_ip
```

### Security Considerations

* Prefer **SSH-2** over the obsolete SSH-1 protocol.
* Protect private keys and use strong passphrases.
* Verify server host keys/fingerprints before trusting them.
* Keep SSH client and server implementations updated.
* Disable weak or deprecated cryptographic algorithms.
* Restrict unnecessary SSH access and forwarding capabilities.

### Common Use Cases

* Remote server administration
* Secure command execution
* Secure file transfer
* Port forwarding
* Network tunneling
* Remote monitoring and management
* Cloud/VM access
* Git repository authentication
* Secure access to embedded and development systems

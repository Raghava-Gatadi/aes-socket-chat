# AES Socket Chat Demo

A Python learning project that combines a handwritten AES implementation with a two-way TCP socket chat. The client and server encrypt messages using a shared key and print the received ciphertext and decrypted text.

## Repository map

| File | Purpose |
| --- | --- |
| [AES.py](AES.py) | AES encryption/decryption implementation |
| [server.py](server.py) | TCP listener and interactive sender/receiver |
| [client.py](client.py) | Connects to the server and exchanges messages |

## Local lab setup

Requires Python 3 and `colorama`. Use an isolated environment:

```sh
python3 -m venv .venv
. .venv/bin/activate
python3 -m pip install colorama
```

Before starting, edit the address in `client.py` to match your lab server. The scripts use port `12345`; the server currently binds all interfaces. Keep the listener on a trusted lab network, or change its bind address to loopback when testing on one computer.

Run the server in one terminal and the client in another:

```sh
python3 server.py
# In the other terminal:
python3 client.py
```

Both sides start with the same demonstration key. A message ending in `\~new_key` changes the key used for subsequent messages; the last delimiter is used. This is application behavior, not an authenticated key-exchange protocol.

## Scope and limitations

This is an educational demonstration, not a secure messaging product. The default key is public, there is no peer authentication, and the socket framing and custom cryptography need independent review. Runtime compatibility and cryptographic correctness were not revalidated during this documentation update.

The original collection is preserved in [cybersecurity](https://github.com/Raghava-Gatadi/cybersecurity).

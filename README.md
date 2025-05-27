# Potlatch

**Potlatch** is a hybrid protocol enabling perfect strangers to anonymously transfer physical goods, without revealing identities, addresses, or transaction metadata. This repository serves as a canonical archive of encrypted dispatches and a living documentation site for the evolving protocol infrastructure.

---

## 🧾 Dispatches

All dispatches are encrypted `.asc` files stored in [`dispatches/encrypted/`](dispatches/encrypted).

Each dispatch is:
- Encrypted with a unique passphrase
- Shared privately via the Buttondown newsletter
- Verified using a SHA256 hash, also sent via email
- Authenticated with a GPG signature of the hash (included inline in the email)

---

### 🔐 To decrypt a dispatch

Download the encrypted `.asc` file and decrypt with:

```bash
gpg --pinentry-mode loopback --output 001-init.txt --decrypt 001-init.asc
```

You will be prompted to enter the passphrase from the newsletter.

Kleopatra users (Windows) can also:
- Download the `.asc` file
- Double-click it to open in Kleopatra
- Enter the passphrase and view the decrypted message

---

### 🧪 To verify integrity and authenticity

1. Run:

```bash
sha256sum 001-init.asc
```

2. Compare the result to the **signed SHA256 hash** block included in the dispatch email

3. To verify the signature on the hash:

```bash
gpg --verify 001-init.sha256.asc
```

You must first import the public key from:

```
https://github.com/potlatch-trade/potlatch/blob/main/keys/potlatch-pgp-public.asc
```

---

> ✨ If the signature is valid and the hash matches, the dispatch is verified as authentic and untampered.

---

## 📁 Repository Structure

```
dispatches/
  encrypted/     → Encrypted dispatch files (.asc format)

keys/            → Public key (optional, unused in symmetric flow)
protocol/        → Documentation and specifications for the Potlatch protocol
src/             → Code for future cryptographic, routing, and escrow tooling
docs/            → Glossary, changelog, and roadmap for Potlatch
```

---

## 📬 Subscribe

To receive dispatches and their decryption keys, subscribe to:

**[https://potlatchtrade.xyz](https://potlatchtrade.xyz)**

---

## 🔐 Philosophy

Potlatch is an experiment in anonymous, trust-minimized, real-world trade in physical goods.  
It rejects surveillance infrastructure and corporate logistics in favor of encrypted networks, local nodes, distributed physical protocols, bridges between physical world and blockchain, blind and ZK verification mechanism, onion-style package routing.

---

## 🪪 Authorship & Integrity

All messages are encrypted and verified out-of-band. Hashes are signed.  
Authenticity is grounded in social trust and verifiable signed hashes.

---

## License

[MIT License](LICENSE)



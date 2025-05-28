# Potlatch

**Potlatch** is a hybrid protocol enabling perfect strangers to anonymously transfer physical goods, without revealing identities, addresses, or transaction metadata. This repository serves as a canonical archive of encrypted dispatches and a living documentation site for the evolving protocol infrastructure.

This repository is **not** yet a showcase of open source code. It is a **living, partial archive**: a record of encrypted dispatches, signed hashes, and the intentional asymmetry between what is revealed and what remains hidden, a play between visibility and invisibility, private and public, social trust and coded trustlessness.

Each commit documents a moment — a packet sent, a cipher seeded, a hash signed and distributed. The project’s form mirrors its politics: **iterative, trustless, and resistant to capture**. What you see here is only one surface of a broader system.

The full protocol, infrastructure, and logic will emerge **piece by piece**, encoded first in practice — not proclamation. If you’d like to receive the encrypted dispatches and witness the unfolding as it happens:

➡️ **[Sign up at https://potlatchtrade.xyz](https://potlatchtrade.xyz)**

---

##  ~P Philosophy

Potlatch is an experiment in anonymous, trust-minimized, real-world trade in physical goods.
It rejects surveillance infrastructure and corporate logistics in favor of encrypted networks, local nodes, distributed physical protocols, bridges between physical world >

---


##  ~A Repository Structure

```
dispatches/
  encrypted/     → Encrypted dispatch files (.asc format)

keys/            → Public key (optional, unused in symmetric flow)
protocol/        → Documentation and specifications for the Potlatch protocol
src/             → Code for future cryptographic, routing, and escrow tooling
docs/            → Glossary, changelog, and roadmap for Potlatch
```

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

Windows users can decrypt Potlatch dispatches with the following method:
- Download and install Gpg4win[https://gpg4win.org](https://gpg4win.org)
- Download the `.asc` file
- Double-click it to open in Kleopatra
- Enter the passphrase and view the decrypted message


MacOS Users can decrypt Potlatch dispatches with the following method:
- Download and install GPG Suite [https://gpgtools.org](https://gpgtools.org)
- Use **GPG Keychain** to import your key and decrypt `.asc` files
- Double-click the encrypted file to decrypt with passphrase

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


## 🪪 Authorship & Integrity

All messages are encrypted and verified out-of-band. Hashes are signed.  
Authenticity is grounded in social trust and verifiable signed hashes.

---

## License

[MIT License](LICENSE)



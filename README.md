# Potlatch

**Potlatch** is a hybrid protocol enabling perfect strangers to anonymously exchange physical goods, without revealing identities, addresses, or transaction metadata. This repository serves as a canonical archive of encrypted dispatches and a living documentation site for the evolving protocol infrastructure.

This repository is **not** yet a showcase of open source code. It is a **living, partial archive**: a record of encrypted dispatches, signed hashes, and the intentional asymmetry between what is revealed and what remains hidden, a play between visibility and invisibility, private and public, social trust and coded trustlessness.

The full protocol, infrastructure, and logic will emerge **piece by piece**, encoded first in practice — not proclamation. If you’d like to receive the encrypted dispatches and witness the unfolding as it happens:

Each commit documents a moment — a packet sent, a cipher seeded, a hash signed and distributed. The project’s form mirrors its politics: **iterative, trustless, and resistant to capture**. What you see here is only one surface of a broader system.

➡️ **[Sign up at https://potlatchtrade.xyz](https://potlatchtrade.xyz)**

---

##  ~P Philosophy

Potlatch is an experiment in anonymous, trust-minimized, real-world trade in physical goods.  
It rejects surveillance infrastructure and corporate logistics in favor of encrypted networks, local nodes, distributed physical protocols, bridges between physical world and digital autonomy.

---

##  ~A Repository Structure

```
dispatches/
  encrypted/       → Encrypted dispatch files (.asc format)
  signed-hashes/   → Signed SHA256 hash files (.sha256.asc)

keys/              → Public key (optional, unused in symmetric flow)
protocol/          → Documentation and specifications for the Potlatch protocol
src/               → Code for future cryptographic, routing, and escrow tooling
docs/              → Glossary, changelog, and roadmap for Potlatch
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

### ~M to decrypt a dispatch

Download the encrypted `.asc` file and decrypt with:

```bash
gpg --pinentry-mode loopback --output 001-init.txt --decrypt 001-init.asc
```

You will be prompted to enter the passphrase from the newsletter.

Windows users can decrypt Potlatch dispatches with the following method:
- Download and install Gpg4win [https://gpg4win.org](https://gpg4win.org)
- Download the `.asc` file
- Double-click it to open in Kleopatra
- Enter the passphrase and view the decrypted message

MacOS users can decrypt Potlatch dispatches with the following method:
- Download and install GPG Suite [https://gpgtools.org](https://gpgtools.org)
- Use **GPG Keychain** to import your key and decrypt `.asc` files
- Double-click the encrypted file to decrypt with passphrase

---

### 🧪 To verify integrity and authenticity

All signed SHA256 hashes are stored in [`dispatches/signed-hashes/`](dispatches/signed-hashes).  
These are signed using GPG and correspond to encrypted files in `dispatches/encrypted/`.

1. Download the encrypted file and the corresponding signed hash:

```bash
curl -O https://github.com/potlatch-trade/potlatch/raw/main/dispatches/encrypted/001-init.asc
curl -O https://github.com/potlatch-trade/potlatch/raw/main/dispatches/signed-hashes/001-init.sha256.asc
```

2. Import the Potlatch public key (if not already done):

```bash
curl -O https://github.com/potlatch-trade/potlatch/raw/main/keys/potlatch-pubkey.asc
gpg --import potlatch-pubkey.asc
```

3. Verify the signature on the signed hash:

```bash
gpg --verify 001-init.sha256.asc
```

4. Check the actual hash value if you want to verify it manually:

```bash
sha256sum 001-init.asc
```

Compare it to the value shown inside the signed `.sha256.asc` file.  
If the signature is valid and the hash matches, the dispatch is verified as authentic and untampered.

---

## 🪪 Authorship & Integrity

All messages are encrypted and verified out-of-band. Hashes are signed.  
Authenticity is grounded in social trust and verifiable signed hashes.

---

## License

[MIT License](LICENSE)

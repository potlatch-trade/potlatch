# Potlatch

**Potlatch** is a hybrid protocol enabling perfect strangers to anonymously trade in tangible goods. This repository serves as both the canonical archive for encrypted dispatches and the evolving development site for the protocol’s specification, logic, and tooling.

---

## 🧾 Dispatches

All dispatches are encrypted `.gpg` files stored in [`dispatches/encrypted/`](dispatches/encrypted).  
Each dispatch has an associated `SHA256` hash stored in [`dispatches/hashes/`](dispatches/hashes) for public verification.

To verify a dispatch:

```bash
sha256sum dispatches/encrypted/001-init.gpg
cat dispatches/hashes/001-init.sha256

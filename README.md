---
description: OpenFilWallet focuses on creating an easy-to-use miner HD wallet
---

# 🌈 What is OpenFilWallet

The goal of OpenFilWallet is to become an easy-to-use miner HD wallet, which is convenient for users to initiate ordinary transactions and multi-signature transactions simply and safely. OpenFilWallet allows users to easily initiate transactions without importing private keys to guardian nodes. OpenFilWallet provides offline functionality, allowing it to act as an offline signature machine, providing maximum security.

OpenFilWallet provides a safe and simple way to send Filecoin transactions, and introduces the mnemonic function to facilitate account management, and ensures wallet security through encryption. The focus is to provide a simple multi-signature transaction experience, lower the threshold for using the multi-signature function, and promote network stability.

## features

* Open source: The OpenFilWallet source code repository is hosted at [github.com/OpenFilWallet/OpenFilWallet](https://github.com/OpenFilWallet/OpenFilWallet)
* HD Wallet: Hierarchical deterministic wallet, manage multiple wallets through mnemonic words.
* Security: Dual password. The private key/mnemonic is encrypted with the `root password`, and the `login password` must be entered to use the wallet. The timeout is not used, and the `login password` needs to be re-entered.
* Permissions: Restrict requests through multi-level tokens.
* Multi-function: built for miner, supports all commonly used multi-signature transactions and ordinary transactions.
* Offline signature: supports offline signature function, outputs signed transactions, and submits transactions through [msgboat](https://github.com/OpenFilWallet/msgboat) service to increase security.


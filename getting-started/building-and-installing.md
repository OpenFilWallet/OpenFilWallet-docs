---
description: Build openfild and Web UI as one binary.
---

# Building and installing

## Prerequisites

Please make sure you have installed:

* **Go (1.19)** - [https://go.dev/learn/](https://go.dev/learn/)
* **Rust** - [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install)
* **Node 16.x -** [https://nodejs.org/dist/v16.15.0/](https://nodejs.org/dist/v16.15.0/)

Linux / MacOS

```
git clone git@github.com:OpenFilWallet/OpenFilWallet.git
cd OpenFilWallet
make all
sudo make install
```

* `make all` :  `filecoin-ffi`, `vue app`, `openfilwallet` will be compiled, `openfild` will package `vue app`, and provide Web UI service on port 8080
* `make ffi`: compile `filecoin-ffi`
* `make vue`: Install and compile the Web UI app
* `make install`: Install executable binaries to `/usr/local/bin/`


# Architecture

OpenFilWallet completely self-manages private keys and mnemonic words, and does not need to import private keys to any Filecoin nodes. You don't need to run a filecoin node to use OpenFilWallet, you can use any public Filecoin node. OpenFilWallet requests Filecoin nodes to obtain the required information and send signed transactions through RPC.



By default, the wallet daemon repository is located in `~/.openfilwallet`

It contains the following files:

* `api` wallet service listening address
* `datastore` wallet database
* `token` The token used when calling wallet endpoints
* `repo.lock` A lock file created when wallet is running

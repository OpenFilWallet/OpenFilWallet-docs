# Binaries

OpenFilWallet contains binaries: `openfil-cli` and `openfild`.

`openfil-cli`: The client command line tool of the wallet, which can interact with the wallet service through this tool.

```
openfil-cli -h
NAME:
   openfil-cli - open source hd wallet client for Filecoin

USAGE:
   openfil-cli [global options] command [command options] [arguments...]

VERSION:
   v0.0.1+git.39300c3

COMMANDS:
   status    query wallet status
   login     login openfil wallet
   logout    logout openfil wallet
   node      The daemon node used by the OpenFilWallet wallet
   chain     Interact with filecoin blockchain
   send      send tx
   sign      sign with the private key at the specified address
   wallet    OpenFilWallet wallet new / list
   transfer  transfer amount
   miner     miner control
   msig      Interact with a multisig wallet
   help, h   Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --help, -h           show help (default: false)
   --verbose, --vv      enables very verbose mode (default: false)
   --version, -v        print the version (default: false)
   --wallet-repo value  Specify openfilwallet repo path. flag(--wallet-repo) or env(OPEN_FIL_WALLET_PATH) (default: "~/.openfilwallet") [$OPEN_FIL_WALLET_PATH]
```

`openfild`: wallet service process, and mnemonic/private key/password management

```
openfild -h
NAME:
   openfild - open source hd wallet for Filecoin

USAGE:
   openfild [global options] command [command options] [arguments...]

VERSION:
   v0.0.1+git.39300c3

COMMANDS:
   init      Initialize a OpenFilWallet repo
   auth      Manage RPC permissions
   run       Start OpenFilWallet process
   mnemonic  OpenFilWallet mnemonic generate / import / export
   wallet    OpenFilWallet wallet list / import / export
   password  OpenFilWallet password settings
   help, h   Shows a list of commands or help for one command

GLOBAL OPTIONS:
   --help, -h           show help (default: false)
   --verbose, --vv      enables very verbose mode (default: false)
   --version, -v        print the version (default: false)
   --wallet-repo value  Specify openfilwallet repo path. flag(--wallet-repo) or env(OPEN_FIL_WALLET_PATH) (default: "~/.openfilwallet") [$OPEN_FIL_WALLET_PATH]
```


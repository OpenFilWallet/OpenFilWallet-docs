# Private Key

The `wallet` command module under `openfild` is responsible for managing wallet private keys, including the functions of create, list, import, export, and delete, all of which require root password for authorization verification. You can use `openfild wallet import` to import the private key from lotus, and the usage style is consistent with lotus.

```
openfild wallet -h
NAME:
   openfild wallet - OpenFilWallet wallet list / import / export

USAGE:
   openfild wallet command [command options] [arguments...]

COMMANDS:
   new      Generate bls and secp256k1 wallets with the same index
   list     wallet list
   import   wallet import
   export   wallet export
   delete   delete private key
   help, h  Shows a list of commands or help for one command

OPTIONS:
   --help, -h  show help (default: false)
```

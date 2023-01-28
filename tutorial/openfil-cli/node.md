# Node

Using OpenFilWallet, there is no need to run a filecoin node. The security of the private key is guaranteed by openFilWallet, so third-party public node services can be used. Such as glif, infura

The OpenFilWallet service has a built-in glif public node, which can be used for node management through the `node` command: node add, update, delete, use, list, best.

```
openfil-cli node -h
NAME:
   openfil-cli node - The daemon node used by the OpenFilWallet wallet

USAGE:
   openfil-cli node command [command options] [arguments...]

COMMANDS:
   add      add a node
   update   update a node
   delete   delete a node
   use      use node
   list     node list
   best     best node
   help, h  Shows a list of commands or help for one command

OPTIONS:
   --help, -h  show help (default: false)
```










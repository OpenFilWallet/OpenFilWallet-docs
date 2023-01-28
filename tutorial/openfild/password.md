# Password

The `password` command module under `openfild` provides management password function, which can update root password or login password.&#x20;

If you forget the root password, you can only reset the wallet by re-importing the mnemonic. There will be no loss of your assets. If you have not backed up the mnemonic, please recall the root password carefully, otherwise there is no other way.

```
NAME:
   openfild password - OpenFilWallet password settings

USAGE:
   openfild password command [command options] [arguments...]

COMMANDS:
   update-root   update root password
   update-login  update login password, need root password
   help, h       Shows a list of commands or help for one command

OPTIONS:
   --help, -h  show help (default: false)
```

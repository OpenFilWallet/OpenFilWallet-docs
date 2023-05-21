# Password

The `password` command module under `openfild` provides management password function, which can update master password or login password.&#x20;

If you forget the master password, you can only reset the wallet by re-importing the mnemonic. There will be no loss of your assets. If you have not backed up the mnemonic, please recall the master password carefully, otherwise there is no other way.

```
openfild password -h
NAME:
   openfild password - OpenFilWallet password settings

USAGE:
   openfild password command [command options] [arguments...]

COMMANDS:
     update-master  update master password
     update-login   update login password, need master password
     help, h        Shows a list of commands or help for one command

OPTIONS:
   --help, -h  show help (default: false)
```

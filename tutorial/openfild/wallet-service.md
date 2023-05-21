# Wallet Service

Run `openfild run`, after entering the master password correctly, the wallet service will be started.

* The wallet service listens to port 6678 by default. Please make sure that port 6678 is open and not occupied. You can also use `--wallet-api` to specify the port.
* The wallet service starts the online function by default, that is, allows the transaction function to be sent. If the offline wallet function is enabled, please specify `--offline`, only the signature service will be provided, and the transaction will not be sent.

```
openfild run -h

NAME:
   openfild run - Start OpenFilWallet process

USAGE:
   openfild run [command options] [arguments...]

OPTIONS:
   --offline           offline wallet (default: false)
   --wallet-api value  wallet api port (default: "6678") [$OPEN_FIL_WALLET_API]
```

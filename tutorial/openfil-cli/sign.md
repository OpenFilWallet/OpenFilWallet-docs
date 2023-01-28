# Sign

Sign command, which can sign message, sign transaction, sign and send transaction.

```
openfil-cli sign -h
NAME:
   openfil-cli sign - sign with the private key at the specified address

USAGE:
   openfil-cli sign command [command options] [arguments...]

COMMANDS:
   sign-msg      sign msg
   sign-tx       sign a transaction
   sign-tx-send  sign a transaction and send tx
   help, h       Shows a list of commands or help for one command

OPTIONS:
   --help, -h  show help (default: false)
```

Example:

sign-msg

```
openfil-cli sign sign-msg f1am2dr43qfy4vhfrxmdbmwzlsa3c3wanzm7dn7my 4300e907
017374d27c6ee9063762772d5cd285065181cba15aaa5ef9ba41f28e7fe67057cc073ee1f8c9dac0daffa86f87ec87dc8c9106c24fce7488c5710eca3af6a0376801
```

sign-tx

```
openfil-cli sign sign-tx --tx-path ./transfer.txt --output ./transfer_sign.txt
```

cat ./transfer\_sign.txt

```
{
  "message": {
    "version": 0,
    "to": "f1am2dr43qfy4vhfrxmdbmwzlsa3c3wanzm7dn7my",
    "from": "f1ys7n5mrm2vtx6coxc5wkmkddan7rznfkax3a6ki",
    "nonce": 43,
    "value": 100000000000000000,
    "gas_limit": 605085,
    "gas_feecap": 101076,
    "gas_premium": 100022,
    "method": 0,
    "params": {
      "name": "",
      "params": ""
    }
  },
  "signature": "584201abc3e2c6cd6ab8fc173b8adb30837bfbf0683aed0ae53b65bb6b3824b875f0451ef33e1f6f119bec6805fa1a658704d8d6f0230b0af63d336e32fcf98807ee5600"
}
```

If `--output` is not specified

```
openfil-cli sign sign-tx --tx-path ./transfer.txt
{
  "message": {
    "version": 0,
    "to": "f1am2dr43qfy4vhfrxmdbmwzlsa3c3wanzm7dn7my",
    "from": "f1ys7n5mrm2vtx6coxc5wkmkddan7rznfkax3a6ki",
    "nonce": 43,
    "value": 100000000000000000,
    "gas_limit": 605085,
    "gas_feecap": 101076,
    "gas_premium": 100022,
    "method": 0,
    "params": {
      "name": "",
      "params": ""
    }
  },
  "signature": "584201abc3e2c6cd6ab8fc173b8adb30837bfbf0683aed0ae53b65bb6b3824b875f0451ef33e1f6f119bec6805fa1a658704d8d6f0230b0af63d336e32fcf98807ee5600"
}
```


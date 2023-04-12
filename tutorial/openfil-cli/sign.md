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
openfil-cli sign sign-msg f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea 4300e907
01a724234cfe981b49ce3684863f04582d23b8b6123fef4032b9f7ce1794d7b94b6095f606899ba048eb586d53231988aafe3a45ec507c4caf8514f7a7d32c423800
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
    "to": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
    "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
    "nonce": 0,
    "value": 1000000000000000000,
    "gas_limit": 2999212,
    "gas_feecap": 103069,
    "gas_premium": 100655,
    "method": 0,
    "params": {
      "name": "",
      "params": ""
    }
  },
  "signature": "58420124b25ab39cd89f488c1fa64768b724db14e3857eb7f62473371817246eb1f9cd4c9e77c467f1522f03758c0b5ce9abb11119b86ded38906c45d4eb4f5c22649201"
}
```

If `--output` is not specified

```
openfil-cli sign sign-tx --tx-path ./transfer.txt
{
  "message": {
    "version": 0,
    "to": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
    "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
    "nonce": 0,
    "value": 1000000000000000000,
    "gas_limit": 2999212,
    "gas_feecap": 103069,
    "gas_premium": 100655,
    "method": 0,
    "params": {
      "name": "",
      "params": ""
    }
  },
  "signature": "58420124b25ab39cd89f488c1fa64768b724db14e3857eb7f62473371817246eb1f9cd4c9e77c467f1522f03758c0b5ce9abb11119b86ded38906c45d4eb4f5c22649201"
}
```


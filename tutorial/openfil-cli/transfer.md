# Transfer

The `openfin-cli transfer` command returns an unsigned transaction that transfer FIl.

```
openfil-cli transfer -h
NAME:
   openfil-cli transfer - transfer amount

USAGE:
   openfil-cli transfer [command options] [from to amount (FIL)]

OPTIONS:
   --gas-feecap value, --gf value   specify gas fee cap to use in AttoFIL (default: "0")
   --gas-limit value, --gl value    specify gas limit (default: 0)
   --gas-premium value, --gp value  specify gas price to use in AttoFIL (default: "0")
   --max-fee value, --mf value      the max tx fee allowed for this transaction (default: "1 FIL")
   --nonce value, -n value          specify the nonce to use (default: 0)
   --output value, -o value         a path to output tx message
```

Explanation of OPTIONS

* `--gas-feecap`, `--gas-limit`, `--gas-premium`, `--max-fee`, `--nonce` are advanced options, you can specify the attributes of the transaction, unless you know what you are doing, you don't need to specify, The wallet service will request the latest status from Filecoin.
* `--output` specifies a file path to save generated transaction, if not specified, the transaction will be output directly in the terminal.

Example:

```
/openfil-cli transfer --output ./transfer.txt  f1ys7n5mrm2vtx6coxc5wkmkddan7rznfkax3a6ki f1am2dr43qfy4vhfrxmdbmwzlsa3c3wanzm7dn7my 0.1
```

cat ./transfer.txt

```
{
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
}
```

If `--output` is not specified

```
openfil-cli transfer  f1ys7n5mrm2vtx6coxc5wkmkddan7rznfkax3a6ki f1am2dr43qfy4vhfrxmdbmwzlsa3c3wanzm7dn7my 0.1

{
  "version": 0,
  "to": "f1am2dr43qfy4vhfrxmdbmwzlsa3c3wanzm7dn7my",
  "from": "f1ys7n5mrm2vtx6coxc5wkmkddan7rznfkax3a6ki",
  "nonce": 43,
  "value": 100000000000000000,
  "gas_limit": 605085,
  "gas_feecap": 101588,
  "gas_premium": 100534,
  "method": 0,
  "params": {
    "name": "",
    "params": ""
  }
}
```

How to sign a transaction, please refer to Sign


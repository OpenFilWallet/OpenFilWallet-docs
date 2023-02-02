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

An unsigned transaction can be made with the following command:

```
openfil-cli transfer -o ./transfer.txt f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a 1
```

cat ./transfer.txt

```
{
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
}
```

If `--output` is not specified

```
openfil-cli transfer f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a 1
{
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
}
```

How to sign a transaction, please refer to Sign


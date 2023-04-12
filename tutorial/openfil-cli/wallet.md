# Wallet

Use `openfil-cli wallet` to create wallet, balance query, wallet list, transaction history.

```
openfil-cli wallet -h
NAME:
   openfil-cli wallet - OpenFilWallet wallet new / list

USAGE:
   openfil-cli wallet command [command options] [arguments...]

COMMANDS:
   new      Generate bls and secp256k1 wallets with the same index
   balance  request wallet balance
   list     wallet list
   history  wallet tx history
   help, h  Shows a list of commands or help for one command

OPTIONS:
   --help, -h  show help (default: false)
```

## create wallet

When creating a wallet, you can use `--index` to specify the path to create the wallet. If it is not specified, it will automatically add 1 to the current wallet index.

Example:

```
openfil-cli wallet new --index 100
f1wt2ugcyksv2ahecxw4av3m6jujciobmvjevk6fy
f3s7bdn5rxbkjyl3vwsjztqhqwlubytgu7pj4vit2ut5crxez7gutezhx6fafnl7cza7g7ztaz77va5xjbftpa
```

Run `openfil-cli wallet list` to view the wallet list:

```
ID      Wallet Type  Address                                                                                 Path
0       secp256k1    f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea                                               m/44'/461'/0'/0/1
1       secp256k1    f1ot2sewu3qj3zy7enskz2umyryo44g2qh6lq5lta                                               m/44'/461'/0'/0/0
2       secp256k1    f1wt2ugcyksv2ahecxw4av3m6jujciobmvjevk6fy                                               m/44'/461'/0'/0/100
3       bls          f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq  m/44'/461'/0'/0/0
4       bls          f3s7bdn5rxbkjyl3vwsjztqhqwlubytgu7pj4vit2ut5crxez7gutezhx6fafnl7cza7g7ztaz77va5xjbftpa  m/44'/461'/0'/0/100
5       bls          f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a  m/44'/461'/0'/0/1
```

## wallet list

When querying the wallet, you can display the wallet balance by specifying `--balance`.

Example:

```
openfil-cli wallet list --balance
ID      Wallet Type  Address                                                                                 Path                 Balance
0       secp256k1    f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea                                               m/44'/461'/0'/0/1    5 FIL
0       secp256k1    f1ot2sewu3qj3zy7enskz2umyryo44g2qh6lq5lta                                               m/44'/461'/0'/0/0    0 FIL
0       secp256k1    f1wt2ugcyksv2ahecxw4av3m6jujciobmvjevk6fy                                               m/44'/461'/0'/0/100  0 FIL
0       bls          f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq  m/44'/461'/0'/0/0    0 FIL
0       bls          f3s7bdn5rxbkjyl3vwsjztqhqwlubytgu7pj4vit2ut5crxez7gutezhx6fafnl7cza7g7ztaz77va5xjbftpa  m/44'/461'/0'/0/100  0 FIL
0       bls          f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a  m/44'/461'/0'/0/1    0 FIL

```

## wallet balance

You can also query the account balance of any wallet address

Example:

```
openfil-cli wallet balance --address f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea
f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea 5 FIL
```

## wallet history

`openfil-cli wallet history` can query local transaction records:

Example:

```
openfil-cli wallet history --address f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea
ID      Version  To                                                                                      From                                       Nonce   Value              GasLimit  GasFeeCap  GasPremium  Method  MsgCid                                                          MsgState
0       0        f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a  f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea  13      10000000000000000  648960    100997     99943       0       bafy2bzacecwt6vpb66pzojouodi4webl5gooyq6vndid2q4dzootmzj4zszt6  success
1       0        f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a  f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea  16      10000000000000000  648960    100905     99809       0       bafy2bzaceb6d2guzm5exp4dbr7ogm5ixd4zof7kwr7vygrxiluy36mpcwp5jg  success
```

# Multi-signature withdraw

Multi-signature wallet withdraw miner's available balance

Example:

Propose

```
openfil-cli msig withdraw-propose --from f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea --miner f02025378 --multisig f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq --output ./withdraw-propose.txt 0.01
```

cat ./withdraw-propose.txt

```
{
  "version": 0,
  "to": "f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq",
  "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
  "nonce": 18,
  "value": 0,
  "gas_limit": 4895711,
  "gas_feecap": 101372,
  "gas_premium": 100318,
  "method": 2,
  "params": {
    "name": "ProposeParams",
    "params": "{\"To\":\"f02025378\",\"Value\":\"0\",\"Method\":16,\"Params\":\"gUgAI4byb8EAAA==\"}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./withdraw-propose.txt --output ./withdraw-propose_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./withdraw-propose_sign.txt
bafy2bzacebj6i4unh57iti56gtf7uoitwbzyyio54uhgotk6kpt5mqh5n4nsa
```

Approve

Msig inspect

```
openfil-cli msig inspect f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq
Balance: 0
Spendable: 0
Threshold: 2 / 3
Signers:
ID         Address
f02025360  f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea
f02025370  f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a
f02025427  f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq
Transactions:  1
ID      State    Approvals  To         Value   Method                           Params
1       pending  1          f02025378  0       new account, unknown method(16)  {"AmountRequested":"10000000000000000"}
```

Approve

```
openfil-cli msig withdraw-approve --from f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a --miner f02025378 --multisig f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq --output ./withdraw-approve.txt 0.01 1 f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea
```

cat ./withdraw-approve.txt

```
{
  "version": 0,
  "to": "f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq",
  "from": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
  "nonce": 6,
  "value": 0,
  "gas_limit": 7985680,
  "gas_feecap": 101696,
  "gas_premium": 100642,
  "method": 3,
  "params": {
    "name": "TxnIDParams",
    "params": "{\"ID\":1,\"ProposalHash\":\"4LZ4W10PsL3+rwA5eiid2mJZIYLezuRqOegbj7n+cNk=\"}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./withdraw-approve.txt --output ./withdraw-approve_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./withdraw-approve_sign.txt
bafy2bzacedprwqms65k4uuvhtr25yxgu6evvuc7xwpatli7b4ypdy2yafwcf6
```


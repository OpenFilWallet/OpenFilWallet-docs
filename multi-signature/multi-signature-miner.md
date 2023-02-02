---
description: >-
  The owner is a multi-signature miner, which can improve node security and
  ensure fund security!
---

# Multi-signature miner

Example of changing the miner owner to a multi-signature wallet

The current owner sends a change owner transaction

```
openfil-cli miner set-owner --actor f02025378 --output ./set-owner.txt  f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a
```

cat ./set-owner.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
  "nonce": 4,
  "value": 0,
  "gas_limit": 3408123,
  "gas_feecap": 101203,
  "gas_premium": 100149,
  "method": 23,
  "params": {
    "name": "Address",
    "params": "f02026065"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./set-owner.txt --output ./set-owner_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./set-owner_sign.txt                                 
bafy2bzacecevusgl3nif3d7c6tjbptkinctcefnz7degfitlthunflq7sk4f6
```

Multi-signature wallet sends confirmation to change owner transaction

Propose

```
openfil-cli msig change-owner-propose --from f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea --miner f02025378 --multisig f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq --output ./change-owner-propose.txt f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq
```

cat ./change-owner-propose.txt

```
{
  "version": 0,
  "to": "f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq",
  "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
  "nonce": 17,
  "value": 0,
  "gas_limit": 4858435,
  "gas_feecap": 101429,
  "gas_premium": 100143,
  "method": 2,
  "params": {
    "name": "ProposeParams",
    "params": "{\"To\":\"f02025378\",\"Value\":\"0\",\"Method\":23,\"Params\":\"RADR1Hs=\"}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./change-owner-propose.txt --output ./change-owner-propose_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./change-owner-propose_sign.txt
bafy2bzacea2ft75io62jzlh5pfx5yhy57wvse77byeioqdgxf64lx3rhizadq
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
0       pending  1          f02025378  0       new account, unknown method(23)  "f02026065"
```

Make approve transaction

```
openfil-cli msig change-owner-approve --from f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a --miner f02025378 --multisig f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq --output ./change-owner-approve.txt f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq 0 f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea
```

cat ./change-owner-approve.txt

```
{
  "version": 0,
  "to": "f2vzjglx5b5wytagquv4koqdpknefekknjnt6fzhq",
  "from": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
  "nonce": 5,
  "value": 0,
  "gas_limit": 9867100,
  "gas_feecap": 101434,
  "gas_premium": 100380,
  "method": 3,
  "params": {
    "name": "TxnIDParams",
    "params": "{\"ID\":0,\"ProposalHash\":\"nbTMwYalIv3XMG0Ie3ThXU/smFgfUvOvkD+lHPAry5Q=\"}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./change-owner-approve.txt --output ./change-owner-approve_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./change-owner-approve_sign.txt                                 
bafy2bzacedngahhhe4vcxfqvah4cwtampipimsddjxmgayjooah2rmykqupg4
```

Query miner information

```
/openfil-cli miner control list --actor f02025378          
owner   f02026065 (multisig) 
name       ID         key                                                                                     balance  
worker     f02025427  f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq  0.1 FIL  
control-0  f02025427  f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq  0.1 FIL
```



Change the miner owner from a multi-signature wallet to a normal wallet, just the opposite of the above process


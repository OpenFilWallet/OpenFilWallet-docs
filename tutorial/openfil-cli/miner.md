# Miner

`openfil-cli miner` contains miner control commands, allowing miner owner to manage miner conveniently

```
openfil-cli miner -h
NAME:
   openfil-cli miner - miner control

USAGE:
   openfil-cli miner command [command options] [arguments...]

COMMANDS:
   withdraw                    withdraw available balance
   set-owner                   Set owner address (this command should be invoked twice, first with the old owner as the senderAddress, and then with the new owner)
   control                     Manage control addresses
   propose-change-worker       Propose a worker address change
   confirm-change-worker       Confirm a worker address change
   propose-change-beneficiary  Propose a beneficiary address change
   confirm-change-beneficiary  Confirm a beneficiary address change
   help, h                     Shows a list of commands or help for one command

OPTIONS:
   --nonce value, -n value          specify the nonce to use (default: 0)
   --gas-premium value, --gp value  specify gas price to use in AttoFIL (default: "0")
   --gas-feecap value, --gf value   specify gas fee cap to use in AttoFIL (default: "0")
   --gas-limit value, --gl value    specify gas limit (default: 0)
   --max-fee value, --mf value      the max tx fee allowed for this transaction (default: "1 FIL")
   --help, -h                       show help (default: false)
```

## miner withdraw

`openfil-cli miner withdraw` - withdraw available balance

Example:

Withdraw transaction

```
openfil-cli miner withdraw --actor f02025378 --output ./withdraw_f02025378.txt 0.01
```

cat ./withdraw\_f02025378.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
  "nonce": 5,
  "value": 0,
  "gas_limit": 3146417,
  "gas_feecap": 100694,
  "gas_premium": 99640,
  "method": 16,
  "params": {
    "name": "WithdrawBalanceParams",
    "params": "{\"AmountRequested\":\"10000000000000000\"}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./withdraw_f02025378.txt --output ./withdraw_f02025378_sign.txt
```

cat ./withdraw\_f02025378\_sign.txt

```
{
  "message": {
    "version": 0,
    "to": "f02025378",
    "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
    "nonce": 5,
    "value": 0,
    "gas_limit": 3146417,
    "gas_feecap": 100694,
    "gas_premium": 99640,
    "method": 16,
    "params": {
      "name": "WithdrawBalanceParams",
      "params": "{\"AmountRequested\":\"10000000000000000\"}"
    }
  },
  "signature": "584201a5f22351c8472292e3be1a8476d4ab3263c68c52b150dba71296793ee0064cfc74cacb93b77c92fbb2b1991a0fbee0c6de01466b510530a94d5d0563bb5102fd00"
}
```

Send transaction

```
openfil-cli send --tx-path ./withdraw_f02025378_sign.txt                                          
bafy2bzaceaornaob6m3jl5dnfb2f46gjsxpvuad3ij36u3cxna72wo2iga7ik
```

## miner control

`openfil-cli miner control` - Manage control addresses

Example:

Get currently set control addresses

```
openfil-cli miner control list --actor f02025378 
name    ID         key                                                                                     balance                   
owner   f02025360  f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea                                               3.009992940960681957 FIL  
worker  f02025370  f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a  1 FIL
```

Set control address

Make an unsigned transaction

```
openfil-cli miner control set --actor f02025378 --output ./control_set.txt  f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq
```

cat ./control\_set.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
  "nonce": 7,
  "value": 0,
  "gas_limit": 4155668,
  "gas_feecap": 101276,
  "gas_premium": 100169,
  "method": 3,
  "params": {
    "name": "ChangeWorkerAddressParams",
    "params": "{\"NewWorker\":\"f02025370\",\"NewControlAddrs\":[\"f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq\"]}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./control_set.txt --output ./control_set_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./control_set_sign.txt
bafy2bzacedy7xtnhhi3lnabous5d5eb6tkkik3d4u5nchsb7bos752ap3pygu
```

## miner set-owner

`openfil-cli miner set-owner` - Set owner address (this command should be invoked twice, first with the old owner as the senderAddress, and then with the new owner)

Example:

Change owner

```
openfil-cli miner set-owner --actor f02025378 --output ./set-owner.txt f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwm
pfexcjdutowp5a6auhl7u3gzb27a f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea 
```

cat ./set-owner.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
  "nonce": 8,
  "value": 0,
  "gas_limit": 3426798,
  "gas_feecap": 101307,
  "gas_premium": 100011,
  "method": 23,
  "params": {
    "name": "Address",
    "params": "f02025370"
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
bafy2bzaceakouyrnjcjfibuevlsst47pyozzzwrerikhhb3makb4ev5r7f3sc
```

Confirm owner

```
openfil-cli miner set-owner --actor f02025378 --output ./confirm-owner.txt f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a
```

cat ./confirm-owner.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
  "nonce": 0,
  "value": 0,
  "gas_limit": 3353091,
  "gas_feecap": 102193,
  "gas_premium": 100264,
  "method": 23,
  "params": {
    "name": "Address",
    "params": "f02025370"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./confirm-owner.txt --output ./confirm-owner_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./confirm-owner_sign.txt                                     
bafy2bzacednkrcikvyvwnvznd2uypcl7z2ywxxogmucksipdchhjdemrftvnm
```

## change-worker

Changing the worker address requires two transactions, Propose and Confirm.

Example:

Propose change worker

```
openfil-cli miner propose-change-worker --actor f02025378 --output ./propose-change-worker.txt f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq
```

cat ./propose-change-worker.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
  "nonce": 1,
  "value": 0,
  "gas_limit": 4037122,
  "gas_feecap": 101917,
  "gas_premium": 100157,
  "method": 3,
  "params": {
    "name": "ChangeWorkerAddressParams",
    "params": "{\"NewWorker\":\"f02025427\",\"NewControlAddrs\":[\"f02025427\"]}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./propose-change-worker.txt --output ./propose-change-worker_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./propose-change-worker_sign.txt                                             
bafy2bzaced5vfvfy2mkgag6ndukqnepzzgzluc53fcjvjfn7jbmyzc3mbszdo
```

Confirm change worker

```
openfil-cli miner confirm-change-worker  --actor f02025378 --output ./confirm-change-worker.txt f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq
```

If you have just sent the propose-change-worker transaction, when you send confirm-change-worker transaction again, an error will be reported:

```
Error: worker key change cannot be confirmed until 2563514, current height is 2562625
```

The reason is, one has to wait some time before sending the confirm-change-worker transaction, which is required by the network. When the block height matches, send confirm-change-worker transaction again and it will succeed

After 900 blocks...

Execute again:

```
openfil-cli miner confirm-change-worker  --actor f02025378 --output ./confirm-change-worker.txt f3qsjierxyqj2ej4uj2ioe7awin63undwb3uyyic6dztvcfumfmjiufnjkjd7q2ohj6hgtcnvqikytzve75zpq
```

cat ./confirm-change-worker.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
  "nonce": 3,
  "value": 0,
  "gas_limit": 3350190,
  "gas_feecap": 101184,
  "gas_premium": 99846,
  "method": 21,
  "params": {
    "name": "",
    "params": ""
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./confirm-change-worker.txt --output ./confirm-change-worker_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./confirm-change-worker_sign.txt
bafy2bzacea6gznrvm7trh7f7veuyxsi2vmmefnyjq2gmiwwrx34b4uzippsyi
```

## change-beneficiary

Changing the beneficiary address requires two transactions, Propose and Confirm.

Example:

Propose change beneficiary

```
openfil-cli miner propose-change-beneficiary  --actor f02025378 --output ./propose-change-beneficiary.txt  f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea 0.1 1000
```

cat ./propose-change-beneficiary.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f3v4kunmpw5wxpc62lhwf57puurye5artjsqmdufmeo3r43tmqkpjkqmwmpfexcjdutowp5a6auhl7u3gzb27a",
  "nonce": 2,
  "value": 0,
  "gas_limit": 3520048,
  "gas_feecap": 103539,
  "gas_premium": 100050,
  "method": 30,
  "params": {
    "name": "ChangeBeneficiaryParams",
    "params": "{\"NewBeneficiary\":\"f02025360\",\"NewQuota\":\"100000000000000000\",\"NewExpiration\":1000}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./propose-change-beneficiary.txt --output ./propose-change-beneficiary_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./propose-change-beneficiary_sign.txt                                                  
bafy2bzacebpmlk33wyknsy7a2g2pzrmdn7ehlcss7sqv6wf6xiqjfnontcjsw
```

Confirm change beneficiary

```
openfil-cli miner confirm-change-beneficiary --new-beneficiary --output ./confirm-change-beneficiary.txt f02025378
```

cat ./confirm-change-beneficiary.txt

```
{
  "version": 0,
  "to": "f02025378",
  "from": "f1e3fkjzjm7wio6bzec5eqesp6khn25smsrvrv2ea",
  "nonce": 9,
  "value": 0,
  "gas_limit": 3596100,
  "gas_feecap": 102774,
  "gas_premium": 99833,
  "method": 30,
  "params": {
    "name": "ChangeBeneficiaryParams",
    "params": "{\"NewBeneficiary\":\"f02025360\",\"NewQuota\":\"100000000000000000\",\"NewExpiration\":1000}"
  }
}
```

Sign transaction

```
openfil-cli sign sign-tx --tx-path ./confirm-change-beneficiary.txt --output ./confirm-change-beneficiary_sign.txt
```

Send transaction

```
openfil-cli send --tx-path ./confirm-change-beneficiary_sign.txt                                           
bafy2bzaced7b4at5g6ngckin2zd543idhu2kvcbbmraukbwj4wmgxgwegn6u2
```


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

# msig

`openfil-cli msig` includes the multi-signature implementation of miner control commands, allowing miner owners to easily use multi-signature management miners, which greatly improves the security of miner.

```
openfil-cli msig -h
NAME:
   openfil-cli msig - Interact with a multisig wallet

USAGE:
   openfil-cli msig command [command options] [arguments...]

COMMANDS:
   create                              Create a new multisig wallet
   list                                msig wallet list
   inspect                             Inspect a multisig wallet
   approve                             Approve a multisig message
   cancel                              Cancel a multisig message
   transfer-propose                    Propose a multisig transaction
   transfer-approve                    Approve a multisig message
   transfer-cancel                     Cancel transfer multisig message
   add-propose                         Propose to add a signer
   add-approve                         Approve a message to add a signer
   add-cancel                          Cancel a message to add a signer
   swap-propose                        Propose to swap signers
   swap-approve                        Approve a message to swap signers
   swap-cancel                         Cancel a message to swap signers
   lock-propose                        Propose to lock up some balance
   lock-approve                        Approve a message to lock up some balance
   lock-cancel                         Cancel a message to lock up some balance
   threshold-propose                   Propose setting a different signing threshold on the account
   threshold-approve                   Approve a message to setting a different signing threshold on the account
   threshold-cancel                    Cancel a message to setting a different signing threshold on the account
   change-owner-propose                Propose an owner address change
   change-owner-approve                Approve an owner address change
   withdraw-propose                    Propose to withdraw FIL from the miner
   withdraw-approve                    Approve to withdraw FIL from the miner
   change-worker-propose               Propose an worker address change
   change-worker-approve               Approve an owner address change
   confirm-change-worker-propose       Confirm an worker address change
   confirm-change-worker-approve       Confirm an worker address change
   set-control-propose                 set control address(-es) propose
   set-control-approve                 set control address(-es) approve
   change-beneficiary-propose          change beneficiary propose
   change-beneficiary-approve          change beneficiary approve
   confirm-change-beneficiary-propose  confirm change beneficiary propose
   confirm-change-beneficiary-approve  confirm change beneficiary approve
   help, h                             Shows a list of commands or help for one command

OPTIONS:
   --nonce value, -n value          specify the nonce to use (default: 0)
   --gas-premium value, --gp value  specify gas price to use in AttoFIL (default: "0")
   --gas-feecap value, --gf value   specify gas fee cap to use in AttoFIL (default: "0")
   --gas-limit value, --gl value    specify gas limit (default: 0)
   --max-fee value, --mf value      the max tx fee allowed for this transaction (default: "1 FIL")
   --help, -h                       show help (default: false)
```

# Wallet init

{% hint style="danger" %}
**Passwords are important:** the `root password` can derive mnemonic phrases. The `login password` can send transactions while the wallet service is running.
{% endhint %}

{% hint style="warning" %}
**Warning**: Be sure to save the root password, otherwise the wallet cannot be started and can only be reset by re-importing the mnemonic
{% endhint %}

Two passwords need to be entered when initializing the wallet:

* `root password`: encrypt the mnemonic and private key
* `login password`: Before using the wallet, the login password is required to log in and unlock the wallet.

Run `openfild init`

```
2023-01-28T18:18:07.512+0800	INFO	openfild	openfild/init.go:19	Initializing OpenFilWallet
2023-01-28T18:18:07.513+0800	INFO	openfild	openfild/init.go:35	Initializing repo
2023-01-28T18:18:07.513+0800	INFO	repo	repo/fsrepo.go:78	Initializing repo at '/Users/zou/.openfilwallet'
Please enter the root password to encrypt the mnemonic and private key
Password:
Confirm Password:
Please enter the login password to login to the wallet
Password:
Confirm Password:
2023-01-28T18:19:51.401+0800	INFO	openfild	openfild/init.go:96	openFilWallet initialized successfully, you can now start it with 'openfild mnemonic generate or openfild mnemonic import'
```

*   The initialization directory of the wallet can be specified by `--wallet-repo`


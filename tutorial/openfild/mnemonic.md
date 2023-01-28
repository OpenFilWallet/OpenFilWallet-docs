# Mnemonic

{% hint style="danger" %}
**Important:** Please back up your mnemonic phrases in a timely and safe manner. it's everything!
{% endhint %}

## generate mnemonic

* When generating the mnemonic, you need to enter the root password set during `openfild init`
* For the newly generated mnemonic phrase, **be sure to export the mnemonic phrase for backup and storage to prevent loss of wallet data or damage to property damage**

Run `openfild mnemonic import`

```
Please enter root password
Password:
Enter Mnemonic key: piece xxx xxx xxx dream
2023-01-28T18:40:20.174+0800	INFO	openfild	openfild/mnemonic.go:125	mnemonic imported successfully
```

## import mnemonic

It is allowed to import external mnemonics, which must comply with the BIP39 specification.

Run `openfild mnemonic import`

```
Please enter root password
Password:
Enter Mnemonic key: piece xxx xxx xxx dream
2023-01-28T18:40:20.174+0800	INFO	openfild	openfild/mnemonic.go:125	mnemonic imported successfully
```

## export mnemonic

Please back up the exported mnemonic safely. **As long as the mnemonic is safe, everything is safe.**

Run `openfild mnemonic export`

```
Please enter root password
Password:
Be sure to save mnemonic. Losing mnemonic will cause all property damage!

piece xxx xxx xxx dream
```

## delete mnemonic

When deleting the mnemonic, you will be asked whether you have backed up the mnemonic, if you have backed up, please enter `y`

Run `openfild mnemonic delete`

```
Please enter root password
Password:
The mnemonic must have been backed up, deletion cannot be undone
Already backed up the mnemonic? [y/n] n
Already backed up the mnemonic? [y/n] n
please back up the mnemonic, run 'openfild mnemonic export'
```

```
Please enter root password
Password:
The mnemonic must have been backed up, deletion cannot be undone
Already backed up the mnemonic? [y/n] y
Already backed up the mnemonic? [y/n] y
2023-01-28T18:42:42.599+0800	INFO	openfild	openfild/mnemonic.go:216	mnemonic deleted successfully
```


# Logout

For the wallet service in the unlocked state, it can be locked by logging out.

Run `openfil-cli logout`

```
sign out successful
```

After logging out, run `openfil-cli status` again, you will get:

```
openfil-cli status 
Wallet Lock:     true
Wallet Offline:  false
Wallet Version:  v0.0.1+git.2b9f02f
```

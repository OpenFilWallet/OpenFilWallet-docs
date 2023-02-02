# Login

For newly launched wallets and wallets that have not been used for more than 10 minutes, they will be locked. The login password password is required to log in to unlock.

Run `openfil-cli login`

```
Please enter login password
Password:
login successful
```

After successful login, run `openfil-cli status` again, you will get:

```
openfil-cli status 
Wallet Lock:     false
Wallet Offline:  false
Wallet Version:  v0.0.1+git.2b9f02f
```

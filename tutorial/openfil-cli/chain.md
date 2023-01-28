# Chain

The `openfil-cli chain` command provides encoding and decoding tools that comply with the Filecoin specification.

```
openfil-cli chain -h
NAME:
   openfil-cli chain - Interact with filecoin blockchain

USAGE:
   openfil-cli chain command [command options] [arguments...]

COMMANDS:
   decode   decode various types
   encode   encode various types
   help, h  Shows a list of commands or help for one command

OPTIONS:
   --help, -h  show help (default: false)
```

Example:

encode:

```
openfil-cli chain encode params --encoding=hex t01000 23 \"t01001\"
"4300e907"
```

decode:

```
openfil-cli chain decode params --encoding=hex  t01000 23 4300e907
"\"f01001\""
```

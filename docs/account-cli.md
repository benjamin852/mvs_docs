### getnewaccount

```
Usage: mvs-cli getnewaccount [-h][--language value] ACCOUNTNAME
ACCOUNTAUTH

Info: Generate a new account from this wallet.

Options (named):

-h [--help] Get a description and instructions for this command.
-l [--language] Options are 'en', 'es', 'ja', 'zh_Hans', 'zh_Hant'
and 'any', defaults to 'en'.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### validateaddress

```
Usage: mvs-cli validateaddress [-h][payment_address]

Info: validateaddress

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

PAYMENT_ADDRESS Valid payment address. If not specified the address
is read from STDIN.
```

### importaccount

```
Usage: mvs-cli importaccount [-h] --accountname value --password value
[--hd_index value][--language value] WORD

Info: importaccount

Options (named):

-h [--help] Get a description and instructions for this command.
-i [--hd_index] Teh HD index for the account.
-l [--language] The language identifier of the dictionary of the
mnemonic. Options are 'en', 'es', 'ja', 'zh_Hans',
'zh_Hant' and 'any', defaults to 'any'.
-n [--accountname] Account name required.
-p [--password] Account password(authorization) required.

Arguments (positional):

WORD The set of words that that make up the mnemonic. If
not specified the words are read from STDIN.
```

### importkeyfile

```
Usage: mvs-cli importkeyfile [-h] FILE

Info: importkeyfile

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

FILE account info file path
```

### dumpkeyfile

```
Usage: mvs-cli dumpkeyfile [-h] ACCOUNTNAME ACCOUNTAUTH LASTWORD
[DESTINATION]

Info: dumpkeyfile

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
LASTWORD The last word of your master private-key phrase.
DESTINATION The keyfile storage path to.
```

### getnewaddress

```
Usage: mvs-cli getnewaddress [-h][--number value] ACCOUNTNAME
ACCOUNTAUTH

Info: Generate new address for this account.

Options (named):

-h [--help] Get a description and instructions for this command.
-n [--number] The address count.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### listaddresses

```
Usage: mvs-cli listaddresses [-h] ACCOUNTNAME ACCOUNTAUTH

Info: List available addresses of this account.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### changepasswd

```
Usage: mvs-cli changepasswd [-h] --password value ACCOUNTNAME ACCOUNTAUTH

Info: changepasswd

Options (named):

-h [--help] Get a description and instructions for this command.
-p [--password] The new password.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### deleteaccount

```
Usage: mvs-cli deleteaccount [-h] ACCOUNTNAME ACCOUNTAUTH LASTWORD

Info: deleteaccount

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
LASTWORD The last word of your private-key phrase.
```

### getaccount

```
Usage: mvs-cli getaccount [-h] ACCOUNTNAME ACCOUNTAUTH LASTWORD

Info: Show account details

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
LASTWORD The last word of your backup words.
```

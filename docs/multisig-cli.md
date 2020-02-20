### createmultisigtx

```
Usage: mvs-cli createmultisigtx [-h][--fee value] ACCOUNTNAME
ACCOUNTAUTH FROMADDRESS TOADDRESS AMOUNT

Info: createmultisigtx

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] Transaction fee. defaults to 10000 ETP bits

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
FROMADDRESS Send from this address
TOADDRESS Send to this address
AMOUNT ETP integer bits.
```

### getpublickey

```
Usage: mvs-cli getpublickey [-h] ACCOUNTNAME ACCOUNTAUTH ADDRESS

Info: getpublickey

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
ADDRESS Address.
```

### deletemultisig

```
Usage: mvs-cli deletemultisig [-h] ACCOUNTNAME ACCOUNTAUTH ADDRESS

Info: deletemultisig

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
ADDRESS The multisig script corresponding address.
```

### getnewmultisig

```
Usage: mvs-cli getnewmultisig [-h] --signaturenum value --publickeynum
value --selfpublickey value [--description value][--publickey value]
ACCOUNTNAME ACCOUNTAUTH

Info: getnewmultisig

Options (named):

-h [--help] Get a description and instructions for this command.
-d [--description] multisig record description.
-k [--publickey] cosigner public key used for multisig
-m [--signaturenum] Account multisig signature number.
-n [--publickeynum] Account multisig public key number.
-s [--selfpublickey] the public key belongs to this account.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### listmultisig

```
Usage: mvs-cli listmultisig [-h] ACCOUNTNAME ACCOUNTAUTH

Info: listmultisig

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### signmultisigtx

```
Usage: mvs-cli signmultisigtx [-hb] ACCOUNTNAME ACCOUNTAUTH TRANSACTION

Info: signmultisigtx

Options (named):

-h [--help] Get a description and instructions for this command.
-b [--broadcast] Broadcast the tx if it is fullly signed.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
TRANSACTION The input Base16 transaction to sign.
```

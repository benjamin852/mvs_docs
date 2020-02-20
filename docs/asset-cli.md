### createasset

```
Usage: mvs-cli createasset [-h] --symbol value --volume value
[--description value][--issuer value] [--decimalnumber value]
ACCOUNTNAME ACCOUNTAUTH

Info: createasset

Options (named):

-h [--help] Get a description and instructions for this command.
-d [--description] The asset description.
-i [--issuer] The asset issuer.defaults to account name.
-n [--decimalnumber] The asset amount decimal number.
-s [--symbol] The asset symbol/name. Global unique.
-v [--volume] The asset maximum supply volume.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### deletelocalasset

```
Usage: mvs-cli deletelocalasset [-h] --symbol value ACCOUNTNAME
ACCOUNTAUTH

Info: deletelocalasset

Options (named):

-h [--help] Get a description and instructions for this command.
-s [--symbol] The asset symbol/name. Global unique.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### getaccountasset

```
Usage: mvs-cli getaccountasset [-h] ACCOUNTNAME ACCOUNTAUTH [SYMBOL]

Info: getaccountasset

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
SYMBOL Asset symbol.
```

### getaddressasset

```
Usage: mvs-cli getaddressasset [-h] ADDRESS

Info: getaddressasset

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ADDRESS address
```

### getasset

```
Usage: mvs-cli getasset [-h][symbol]

Info: Show existed assets details from MVS blockchain.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

SYMBOL Asset symbol. If not specified, will show whole
network asset symbols.
```

### issue

```
Usage: mvs-cli issue [-h][--fee value] ACCOUNTNAME ACCOUNTAUTH SYMBOL

Info: issue

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] The fee of tx. default_value 10 etp

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
SYMBOL issued asset symbol
```

### issuefrom

```
Usage: mvs-cli issuefrom [-h][--fee value] ACCOUNTNAME ACCOUNTAUTH
ADDRESS SYMBOL

Info: issuefrom

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] The fee of tx. default_value 10 etp

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
ADDRESS target address
SYMBOL issued asset symbol
```

### listassets

```
Usage: mvs-cli listassets [-h][accountname] [ACCOUNTAUTH]

Info: list assets details.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### sendasset

```
Usage: mvs-cli sendasset [-h][--fee value] ACCOUNTNAME ACCOUNTAUTH
ADDRESS SYMBOL AMOUNT

Info: sendasset

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] Transaction fee. defaults to 10000 ETP bits

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
ADDRESS Asset receiver.
SYMBOL Asset symbol/name.
AMOUNT Asset integer bits. see asset <decimal_number>.
```

### sendassetfrom

```
Usage: mvs-cli sendassetfrom [-h][--fee value] ACCOUNTNAME ACCOUNTAUTH
FROMADDRESS TOADDRESS SYMBOL AMOUNT

Info: sendassetfrom

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] Transaction fee. defaults to 10000 ETP bits

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
FROMADDRESS From address
TOADDRESS Target address
SYMBOL Asset symbol
AMOUNT Asset integer bits. see asset <decimal_number>.
```

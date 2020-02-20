### gettx

```
Usage: mvs-cli gettx [-h] HASH [JSON]

Info: gettx alias as fetch-tx/gettransaction

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

JSON Json/Raw format, default is '--json=true'.
HASH The Base16 transaction hash of the transaction to
get. If not specified the transaction hash is read
from STDIN.
```

### listtxs

```
Usage: mvs-cli listtxs [-h][--address value] [--height value][--index value] [--limit value][--symbol value] ACCOUNTNAME ACCOUNTAUTH

Info: List transactions details of this account.

Options (named):

-h [--help] Get a description and instructions for this command.
-a [--address] Address.
-e [--height] Get tx according height eg: -e
start-height:end-height will return tx between
[start-height, end-height)
-i [--index] Page index.
-l [--limit] Transaction count per page.
-s [--symbol] Asset symbol.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

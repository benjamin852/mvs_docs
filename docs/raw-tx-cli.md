### createrawtx

```
Usage: mvs-cli createrawtx [-h] --receivers value --senders value --type
value [--deposit value][--fee value] [--message value][--mychange value] [--symbol value]

Info: createrawtx

Options (named):

-d [--deposit] Deposits support [7, 30, 90, 182, 365] days.
defaluts to 7 days
-f [--fee] Transaction fee. defaults to 10000 ETP bits
-h [--help] Get a description and instructions for this command.
-i [--message] Message/Information attached to this transaction
-m [--mychange] Mychange to this address, includes etp and asset
change
-n [--symbol] asset name, not specify this option for etp tx
-r [--receivers] Send to [address:amount]. amount is asset number if
sybol option specified
-s [--senders] Send from addresses
-t [--type] Transaction type. 0 -- transfer etp, 1 -- deposit
etp, 3 -- transfer asset, 6 -- just only send
message
```

### signrawtx

```
Usage: mvs-cli signrawtx [-h] ACCOUNTNAME ACCOUNTAUTH TRANSACTION

Info: signrawtx

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
TRANSACTION The input Base16 transaction to sign.
```

### decoderawtx

```
Usage: mvs-cli decoderawtx [-h] TRANSACTION

Info: decoderawtx

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

TRANSACTION The input Base16 transaction to sign.
```

### sendrawtx

```
Usage: mvs-cli sendrawtx [-h][--fee value] TRANSACTION

Info: sendrawtx

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] The max tx fee. default_value 10 etp

Arguments (positional):

TRANSACTION The input Base16 transaction to broadcast.
```

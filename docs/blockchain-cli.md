### shutdown

```
Usage: mvs-cli shutdown [-h][accountname] [ACCOUNTAUTH]

Info: stop mvsd.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name.
ACCOUNTAUTH Account password/authorization.
```

### getinfo

```
Usage: mvs-cli getinfo [-h]

Info: getinfo

Options (named):

-h [--help] Get a description and instructions for this command.
```

### getheight

```
Usage: mvs-cli getheight [-h]

Info: Get last height. Alias as fetch-height.

Options (named):

-h [--help] Get a description and instructions for this command.
getpeerinfo
Usage: mvs-cli getpeerinfo [-h]

Info: getpeerinfo

Options (named):

-h [--help] Get a description and instructions for this command.
```

### getmininginfo

```
Usage: mvs-cli getmininginfo [-h]

Info: getmininginfo

Options (named):

-h [--help] Get a description and instructions for this command.
```

### startmining

```
Usage: mvs-cli startmining [-h] ACCOUNTNAME ACCOUNTAUTH

Info: start CPU solo mining. You have to setminingaccount firstly.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### stopmining

```
Usage: mvs-cli stopmining [-h][accountname] [ACCOUNTAUTH]

Info: stop CPU solo mining.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### getwork

```
Usage: mvs-cli getwork [-h][accountname] [ACCOUNTAUTH]

Info: getwork to get mining info

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Mining account name required.
ACCOUNTAUTH Mining account password(authorization) required.
```

### addnode

```
Usage: mvs-cli addnode [-h] ACCOUNTNAME ACCOUNTAUTH

Info: addnode

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### setminingaccount

```
Usage: mvs-cli setminingaccount [-h] ACCOUNTNAME ACCOUNTAUTH
PAYMENT_ADDRESS

Info: setminingaccount when pool mining.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
PAYMENT_ADDRESS the payment address of this account.
```

### submitwork

```
Usage: mvs-cli submitwork [-h] NOUNCE HEADERHASH MIXHASH

Info: submitwork to submit mining result.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

NOUNCE nounce.
HEADERHASH header hash.
MIXHASH mix hash.
```

### getmemorypool

```
Usage: mvs-cli getmemorypool [-h][--json value]

Info: Returns all transactions in memory pool.

Options (named):

-h [--help] Get a description and instructions for this command.
-j [--json] Json format or Raw format, default is Json(true).
```

# Block

### getblock

```
Usage: mvs-cli getblock [-h] HASH_OR_HEIGH [JSON][tx_json]

Info: Get sepcified block header from wallet.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

HASH_OR_HEIGH block hash or block height
JSON Json/Raw format, default is '--json=true'.
TX_JSON Json/Raw format for txs, default is
'--tx_json=true'.
```

### getblockheader

```
Usage: mvs-cli getblockheader [-h][--hash value] [--height value]

Info: getblockheader, alias as
fetch-header/getbestblockhash/getbestblockheader.

Options (named):

-h [--help] Get a description and instructions for this command.
-s [--hash] The Base16 block hash.
-t [--height] The block height.
```

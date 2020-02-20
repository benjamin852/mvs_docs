### getbalance

```
Usage: mvs-cli getbalance [-h] ACCOUNTNAME ACCOUNTAUTH

Info: Show total balance details of this account.

Options (named):

-h [--help] Get a description and instructions for this command.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### listbalances

```
Usage: mvs-cli listbalances [-hn][--greater_equal value] [--lesser_equal
value] ACCOUNTNAME ACCOUNTAUTH

Info: List balance details of each address of this account. defaults show
non-zero unspent address.

Options (named):

-g [--greater_equal] Greater than ETP bits.
-h [--help] Get a description and instructions for this command.
-l [--lesser_equal] Lesser than ETP bits.
-n [--nozero] Defaults to true.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

### deposit

```
Usage: mvs-cli deposit [-h][--address value] [--deposit value][--fee value] ACCOUNTNAME ACCOUNTAUTH AMOUNT

Info: Deposit some etp, then get reward for frozen some etp.

Options (named):

-h [--help] Get a description and instructions for this command.
-a [--address] The deposit target address.
-d [--deposit] Deposits support [7, 30, 90, 182, 365] days.
defaluts to 7 days
-f [--fee] Transaction fee. defaults to 10000 ETP bits

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
AMOUNT ETP integer bits.
```

### send

```
Usage: mvs-cli send [-h][--fee value] [--memo value] ACCOUNTNAME
ACCOUNTAUTH TOADDRESS AMOUNT

Info: send etp to a targert address, mychange goes to another existed
address of this account.

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] Transaction fee. defaults to 10000 etp bits
-m [--memo] Attached memo for this transaction.

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
TOADDRESS Send to this address
AMOUNT ETP integer bits.
```

### sendfrom

```
Usage: mvs-cli sendfrom [-h][--fee value] [--memo value] ACCOUNTNAME
ACCOUNTAUTH FROMADDRESS TOADDRESS AMOUNT

Info: send etp from a specified address of this account to target
address, mychange goes to from_address.

Options (named):

-h [--help] Get a description and instructions for this command.
-f [--fee] Transaction fee. defaults to 10000 ETP bits
-m [--memo] The memo to descript transaction

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
FROMADDRESS Send from this address
TOADDRESS Send to this address
AMOUNT ETP integer bits.
```

### sendmore

```
Usage: mvs-cli sendmore [-h] --receivers value [--fee value][--mychange value] ACCOUNTNAME ACCOUNTAUTH

Info: send etp to multi target addresses, must specify mychange address.
Eg: [sendmore $name $password -r $address1:$amount1 -r $address2:$amount2
-m $mychange_address]

Options (named):

-h [--help] Send to more target.
-f [--fee] Transaction fee. defaults to 10000 ETP bits
-m [--mychange] Mychange to this address
-r [--receivers] Send to [address:etp_bits].

Arguments (positional):

ACCOUNTNAME Account name required.
ACCOUNTAUTH Account password(authorization) required.
```

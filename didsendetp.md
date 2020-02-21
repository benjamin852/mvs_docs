# DID Send ETP Or Asset

### Send etp to other digital identities

Compatible with send interface

    Command:
    $ didsend
    Usage: mvs-cli didsend [-h] [--fee value] [--memo value] ACCOUNTNAME
    ACCOUNTAUTH TODID/TOADDRESS AMOUNT

    Info: send etp to a targert did/address, mychange goes to another existed
    address of this account.

    Options (named):

    -h [--help]          Get a description and instructions for this command.
    -f [--fee]           Transaction fee. defaults to 10000 etp bits
    -m [--memo]          Attached memo for this transaction.

    Arguments (positional):

    ACCOUNTNAME          Account name required.
    ACCOUNTAUTH          Account password(authorization) required.
    TODID/TOADDRESS      Send to this did/address
    AMOUNT               ETP integer bits.
    Rule:
    Target can be did or address

Example: Send to specific DID

    Command:
    $ ./mvs-cli didsend test 123 test.mvs 10000
    Output：
    {
        "transaction" :
        {
            "hash" : "d80b49572c9f2ffacb99a6371ce1ba8089712c3c1df9e0ce6a473229977e12f6",
            "inputs" :
            [
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "previous_output" :
                    {
                        "hash" : "cbfa806c1d11f242cf8942a8ef11ff91bbdb80fb44fcb6e26c7892a5af1038fb",
                        "index" : 0
                    },
                    "script" : "[ 3045022100b4ce8d84d69a5f8a67add65919ec12cb8549ce0428f3125b3f9cbc9234dc7d6702202f1808f48012cea6528635785a099c17f30b0c2ba3ce81e9c9cfb9f733e7bc0a01 ] [ 0380990a7312b87abda80e5857ee6ebf798a2bf62041b07111287d19926c429d11 ]",
                    "sequence" : 4294967295
                }
            ],
            "lock_time" : "0",
            "outputs" :
            [
                {
                    "address" : "M9kDHsDKJj9hM8FzSmDu4xCDbo2DFzUhzj",
                    "attachment" :
                    {
                        "from_did" : "",
                        "to_did" : "test.mvs",
                        "type" : "etp"
                    },
                    "index" : 0,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 143f0fc7d1186851be00b48bf526964b776af83b ] equalverify checksig",
                    "value" : 10000
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "attachment" :
                    {
                        "type" : "etp"
                    },
                    "index" : 1,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 8b24031888c2896cedb764012677868b5c64ef3b ] equalverify checksig",
                    "value" : 299990000
                }
            ],
            "version" : "4"
        }
    }

## Send etp from specified DID

Compatible with sendfrom

    Command：
    \$ didsendfrom
    Usage: mvs-cli didsendfrom [-h][--fee value] [--memo value] ACCOUNTNAME
    ACCOUNTAUTH FROMDID/FROMADDRESS TODID/TOADDRESS AMOUNT

    Info: send etp from a specified did/address of this account to target
    did/address, mychange goes to from_did/address.

    Options (named):

    -h [--help] Get a description and instructions for this command.
    -f [--fee] Transaction fee. defaults to 10000 ETP bits
    -m [--memo] The memo to descript transaction

    Arguments (positional):

    ACCOUNTNAME Account name required.
    ACCOUNTAUTH Account password(authorization) required.
    FROMDID/FROMADDRESS Send from this did/address
    TODID/TOADDRESS Send to this did/address
    AMOUNT ETP integer bits.
    Rules:
    FROMDID / FROMADDRESS is the did or address under the current account

Example: Send to specified DID

    Command:
    $ ./mvs-cli didsendfrom Alice 123  ALICE.DIID test.mvs 10000
    Output：
    {
        "transaction" :
        {
            "hash" : "df96c21487d697c45b94fe60188b070b7b23efc5074d02e89b84dca90dff964e",
            "inputs" :
            [
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "previous_output" :
                    {
                        "hash" : "2ffe76571564b69b1940c54c50120c2e98e20b13b141d4d7dba8d95731a2f970",
                        "index" : 1
                    },
                    "script" : "[ 3044022068060af455f5cf648d7dd846cba583947961a3dc17859eadd1a1b7163e58979402207c692e24edd83ec97f3eddf54bb7789ff305cc7b7e349e76872c371d7c0b08ca01 ] [ 0380990a7312b87abda80e5857ee6ebf798a2bf62041b07111287d19926c429d11 ]",
                    "sequence" : 4294967295
                }
            ],
            "lock_time" : "0",
            "outputs" :
            [
                {
                    "address" : "M9kDHsDKJj9hM8FzSmDu4xCDbo2DFzUhzj",
                    "attachment" :
                    {
                        "from_did" : "ALICE.DIID",
                        "to_did" : "test.mvs",
                        "type" : "etp"
                    },
                    "index" : 0,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 143f0fc7d1186851be00b48bf526964b776af83b ] equalverify checksig",
                    "value" : 10000
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "attachment" :
                    {
                        "type" : "etp"
                    },
                    "index" : 1,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 8b24031888c2896cedb764012677868b5c64ef3b ] equalverify checksig",
                    "value" : 299960000
                }
            ],
            "version" : "4"
        }
    }

### Send to multiple DID

Compatible with sendmore

    Command：
    \$ didsendmore
    Usage: mvs-cli didsendmore [-h] --receivers value [--fee value][--mychange value] ACCOUNTNAME ACCOUNTAUTH

    Info: send etp to multi target did/addresses. Eg: [didsendmore $name
    $password -r $did1/address1:$amount1 -r $did2/address2:$amount2 -m
    $mychange_address]

    Options (named):

    -h [--help] Send to more target.
    -f [--fee] Transaction fee. defaults to 10000 ETP bits
    -m [--mychange] Mychange to this did/address
    -r [--receivers] Send to [did/address:etp_bits].

    Arguments (positional):

    ACCOUNTNAME Account name required.
    ACCOUNTAUTH Account password(authorization) required.

    Rules
    "-r" option specifies the destination DID (or address) and amount, you can add multiple;
    "-m" option specifies the DID or address of change

Example: Send to multiple DID or addresses

    Command：
    $ ./mvs-cli didsendmore test 123 -r BOB.DIID:10000  -r M9kDHsDKJj9hM8FzSmDu4xCDbo2DFzUhzj:10000 -m MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo
    {
        "transaction" :
        {
            "hash" : "efeceb068f7fff776b50d0a8d5d89e9f5ac7d1b85ed22f7efb9c83ae7fb3e7f7",
            "inputs" :
            [
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "previous_output" :
                    {
                        "hash" : "4b702213d37c7c0f42b9e654ca7734ac6f64abbf38c145d96790512224e5f05d",
                        "index" : 1
                    },
                    "script" : "[ 304402206e98df433008c0e837545807747583ed7717b7b1b42a3df4305c43bd1ef8cfa7022069056ae0a6f6dbb0bf6e23d2bab884588360b7375b74a5b21cf557409dc155f301 ] [ 0380990a7312b87abda80e5857ee6ebf798a2bf62041b07111287d19926c429d11 ]",
                    "sequence" : 4294967295
                }
            ],
            "lock_time" : "0",
            "outputs" :
            [
                {
                    "address" : "MRyes39YXS3MJLf2fNVTtriVRY93v5HARr",
                    "attachment" :
                    {
                        "from_did" : "",
                        "to_did" : "BOB.DIID",
                        "type" : "etp"
                    },
                    "index" : 0,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ c64bd3fb0959db9212066496275e4d5a858f3e5e ] equalverify checksig",
                    "value" : 10000
                },
                {
                    "address" : "M9kDHsDKJj9hM8FzSmDu4xCDbo2DFzUhzj",
                    "attachment" :
                    {
                        "type" : "etp"
                    },
                    "index" : 1,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 143f0fc7d1186851be00b48bf526964b776af83b ] equalverify checksig",
                    "value" : 10000
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "attachment" :
                    {
                        "type" : "etp"
                    },
                    "index" : 2,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 8b24031888c2896cedb764012677868b5c64ef3b ] equalverify checksig",
                    "value" : 73073199
                }
            ],
            "version" : "4"
        }
    }

### Send assets to other DID

    Command：
    $ didsendasset
    Usage: mvs-cli didsendasset [-h] [--fee value] [--model value]
    ACCOUNTNAME ACCOUNTAUTH TODID/TOADDRESS ASSET AMOUNT

    Info: didsendasset

    Options (named):

    -h [--help]          Get a description and instructions for this command.
    -f [--fee]           Transaction fee. defaults to 10000 ETP bits
    -m [--model]         The token offering model by block height. TYPE=1 -
                        fixed quantity model; TYPE=2 - specify parameters;
                        LQ - Locked Quantity each period; LP - Locked
                        Period, numeber of how many blocks; UN - Unlock
                        Number, number of how many LPs; eg:
                        TYPE=1;LQ=9000;LP=60000;UN=3
                        TYPE=2;LQ=9000;LP=60000;UN=3;UC=20000,20000,20000;UQ=3000,3000,3000
                        defaults to disable.

    Arguments (positional):

    ACCOUNTNAME          Account name required.
    ACCOUNTAUTH          Account password(authorization) required.
    TODID/TOADDRESS      Asset receiver did/address.
    ASSET                Asset MST symbol.
    AMOUNT               Asset integer bits. see asset <decimal_number>.
    Rule:
    target can be a valid DID or address

Example: Send asset to specified DID

    Command:
    $ ./mvs-cli didsendasset test 123 BOB.DIID TEST.AST 10
    {
        "transaction" :
        {
            "hash" : "adb3509703c987a6c182d104426274d55ea8d8c5a50ccefda621e6e58a6f94b6",
            "inputs" :
            [
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "previous_output" :
                    {
                        "hash" : "42e31a42ac1faf15c55431137a4940d082a9a513e8e1d1d39cba503e6b9890d0",
                        "index" : 0
                    },
                    "script" : "[ 3045022100f995721c4d0b9468c6e64557f6b7d34ed81a1ed12dd516b25a5758c34a3ab5570220713b06b4041d74e509a557d3ee4637ef51fd9c42baac58f5796cb0bad33f4e4801 ] [ 0380990a7312b87abda80e5857ee6ebf798a2bf62041b07111287d19926c429d11 ]",
                    "sequence" : 4294967295
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "previous_output" :
                    {
                        "hash" : "421a2ea3eb45c67dd815a2a0f2de475aac08355134d33c92f9ee0dff20cc1498",
                        "index" : 2
                    },
                    "script" : "[ 304502210096a9e1b48a2fc0ee86e2af01cb200ce8f2d06abe7e24de28b1bc2ade6ed2133602205e6feb6fbfcdfc92a55612f927ed729bc19c415e2f4d566e03d5ba4102fb659c01 ] [ 0380990a7312b87abda80e5857ee6ebf798a2bf62041b07111287d19926c429d11 ]",
                    "sequence" : 4294967295
                }
            ],
            "lock_time" : "0",
            "outputs" :
            [
                {
                    "address" : "MRyes39YXS3MJLf2fNVTtriVRY93v5HARr",
                    "attachment" :
                    {
                        "from_did" : "",
                        "quantity" : 10,
                        "symbol" : "TEST.AST",
                        "to_did" : "BOB.DIID",
                        "type" : "asset-transfer"
                    },
                    "index" : 0,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ c64bd3fb0959db9212066496275e4d5a858f3e5e ] equalverify checksig",
                    "value" : 0
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "attachment" :
                    {
                        "type" : "etp"
                    },
                    "index" : 1,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 8b24031888c2896cedb764012677868b5c64ef3b ] equalverify checksig",
                    "value" : 299990000
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "attachment" :
                    {
                        "quantity" : 299969,
                        "symbol" : "TEST.AST",
                        "type" : "asset-transfer"
                    },
                    "index" : 2,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 8b24031888c2896cedb764012677868b5c64ef3b ] equalverify checksig",
                    "value" : 0
                }
            ],
            "version" : "4"
        }
    }

### Send assets from the current DID

    Command:
    $ didsendassetfrom
    Usage: mvs-cli didsendassetfrom [-h] [--fee value] [--model value]
    ACCOUNTNAME ACCOUNTAUTH FROMDID/FROMADDRESS TODID/TOADDRESS SYMBOL AMOUNT

    Info: didsendassetfrom

    Options (named):

    -h [--help]          Get a description and instructions for this command.
    -f [--fee]           Transaction fee. defaults to 10000 ETP bits
    -m [--model]         The token offering model by block height. TYPE=1 -
                        fixed quantity model; TYPE=2 - specify parameters;
                        LQ - Locked Quantity each period; LP - Locked
                        Period, numeber of how many blocks; UN - Unlock
                        Number, number of how many LPs; eg:
                        TYPE=1;LQ=9000;LP=60000;UN=3
                        TYPE=2;LQ=9000;LP=60000;UN=3;UC=20000,20000,20000;UQ=3000,3000,3000
                        defaults to disable.

    Arguments (positional):

    ACCOUNTNAME          Account name required.
    ACCOUNTAUTH          Account password(authorization) required.
    FROMDID/FROMADDRESS  From did/address
    TODID/TOADDRESS      Target did/address
    SYMBOL               Asset symbol
    AMOUNT               Asset integer bits. see asset <decimal_number>.
    Rule:
    Can be a valid DID or address

Example: Send asset to specified did

    Command:
    $ ./mvs-cli didsendassetfrom Alice 123 ALICE.DIID BOB.DIID  ALICE.AST 10
    {
        "transaction" :
        {
            "hash" : "466041cd360b2111c3b92666d3815e0923a7f91352c95029115703edb09e42a4",
            "inputs" :
            [
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "previous_output" :
                    {
                        "hash" : "f8dcd9379023752f64943fb4a66f067a381b1e0044cd5627d2e83fb98ec4487b",
                        "index" : 0
                    },
                    "script" : "[ 304402200a03257b07dc5ca1ca15c10fbbf6196c04a14bdd608358f2fd70d68d49076b67022036fbb9c0499ce66b4b4d78a8813a0617078880562261ce23d91a0f463e3ff52601 ] [ 0380990a7312b87abda80e5857ee6ebf798a2bf62041b07111287d19926c429d11 ]",
                    "sequence" : 4294967295
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "previous_output" :
                    {
                        "hash" : "adb3509703c987a6c182d104426274d55ea8d8c5a50ccefda621e6e58a6f94b6",
                        "index" : 2
                    },
                    "script" : "[ 304402206061388fb8c00c3534c81de1379dfd78d1837a511dfd6fef688ec7ca7fb2f129022039c69eee33ab092cce3d6e6fc643beb8677155071a0b9affdf0a55fff3bfea4b01 ] [ 0380990a7312b87abda80e5857ee6ebf798a2bf62041b07111287d19926c429d11 ]",
                    "sequence" : 4294967295
                }
            ],
            "lock_time" : "0",
            "outputs" :
            [
                {
                    "address" : "MRyes39YXS3MJLf2fNVTtriVRY93v5HARr",
                    "attachment" :
                    {
                        "from_did" : "ALICE.DIID",
                        "quantity" : 10,
                        "symbol" : "ALICE.AST",
                        "to_did" : "BOB.DIID",
                        "type" : "asset-transfer"
                    },
                    "index" : 0,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ c64bd3fb0959db9212066496275e4d5a858f3e5e ] equalverify checksig",
                    "value" : 0
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "attachment" :
                    {
                        "type" : "etp"
                    },
                    "index" : 1,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 8b24031888c2896cedb764012677868b5c64ef3b ] equalverify checksig",
                    "value" : 299990000
                },
                {
                    "address" : "MLasJFxZQnA49XEvhTHmRKi2qstkj9ppjo",
                    "attachment" :
                    {
                        "quantity" : 299959,
                        "symbol" : "ALICE.AST",
                        "type" : "asset-transfer"
                    },
                    "index" : 2,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 8b24031888c2896cedb764012677868b5c64ef3b ] equalverify checksig",
                    "value" : 0
                }
            ],
            "version" : "4"
        }
    }

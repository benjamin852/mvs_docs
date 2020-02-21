# Digital Identity Transfer

The digital identity can be migrated by changing the address;
if you want to transfer the digital identity from user 1 to user 2, you can first transfer to the multi-signature address of two people, and then transfer from the multi-signature address to the public key address of user 2 each time The process requires multi-signature confirmation and a certain fee;
transfer of digital identity requires verification of the current account and destination address. If you need to migrate to a multi-signature address, multiple people need to confirm the signature of the migration transaction.

    Command:
    $ didchangeaddress
    Usage: mvs-cli didchangeaddress [-h] [--fee value] ACCOUNTNAME
    ACCOUNTAUTH TOADDRESS DIDSYMBOL

    Info: didchangeaddress

    Options (named):

    -h [--help]          Get a description and instructions for this command.
    -f [--fee]           Transaction fee. defaults to 10000 ETP bits

    Arguments (positional):

    ACCOUNTNAME          Account name required.
    ACCOUNTAUTH          Account password(authorization) required.
    TOADDRESS            Target address
    DIDSYMBOL            Did symbol

    Rule：
    TOADDRESS is a valid address under the current account and is not bound to another did

1.  Example: transfer did to another address of the current account

        Command:
        $ /mvs-cli didchangeaddress test 123 MP5FoYQHiEQ52pcEURkaYmuqZMnYHNAZ83 test.mvs

        输出：
        {
            "transaction" :
            {
                "hash" : "018a877766c95f97bbf8d710867a4a4266eeb2c12fa16442166f7e5c411a1ac1",
                "inputs" :
                [
                    {
                        "address" : "MP5FoYQHiEQ52pcEURkaYmuqZMnYHNAZ83",
                        "previous_output" :
                        {
                            "hash" : "e38c3347b2d23dc0dd524c3cad5bd75835e787b4abb0baee67b0f93a7d988805",
                            "index" : 0
                        },
                        "script" : "[ 30440220242c0e31ffc0ba07874f4910e7ec10070c1004d1eeb0fe4f95943565ba615b7602203b3889a281f0f2f2dcff2a29419d14998e7910f74acacf328ea495a3171f3e6c01 ] [ 028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab2 ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu",
                        "previous_output" :
                        {
                            "hash" : "4d5ae5bfdd89d30a771680cd3080478e741ff1bea65b4903ea42160952c0c9e8",
                            "index" : 0
                        },
                        "script" : "[ 304502210099ba2727501df331fc9c48095c117adfd5a58ee8950b9610ce39de026d3ff01c02207aa5de45c6546b46113cd8e2c0fa44762600d1db7b27d26e6d13e5acf4dc8fe401 ] [ 035f572a164ec0e7d8f1935e357d86c6441152bed7251389a1c66174ae890dad90 ]",
                        "sequence" : 4294967295
                    }
                ],
                "lock_time" : "0",
                "outputs" :
                [
                    {
                        "address" : "MP5FoYQHiEQ52pcEURkaYmuqZMnYHNAZ83",
                        "attachment" :
                        {
                            "address" : "MP5FoYQHiEQ52pcEURkaYmuqZMnYHNAZ83",
                            "symbol" : "test.mvs",
                            "type" : "did-transfer"
                        },
                        "index" : 0,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ a672b25c96da4a80a1f0f78d44515716e776d52a ] equalverify checksig",
                        "value" : 0
                    }
                ],
                "version" : "4"
            }
        }

        After waiting for the transaction to enter the block, check the migration record command of:
        $ ./mvs-cli getdid test.mvs
        output:
        {
            "addresses" :
            [
                {
                    "address" : "MP5FoYQHiEQ52pcEURkaYmuqZMnYHNAZ83",
                    "status" : "current"
                },
                {
                    "address" : "M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu",
                    "status" : "history"
                }
            ],
            "did" : "test.mvs"
        }

2.  Example: transfer did to a multi-signature address, 35cY636TPTfFW8PxhqH3BNRL54g1T4mbR2 is a multi-signature address for test and test 2


        Command：
        $ ./mvscli didchangeaddress test 123 35cY636TPTfFW8PxhqH3BNRL54g1T4mbR2 test.mvs
        输出:
        0400000002e2ff847f7f660baae489cc219c25982b6b6c00afddc238ad92767017246917c00000000093004830450221009f620f2316ce9b5d803f7651e09971443d6cb46da47619f870148551d29ac00f022016aa63ffde9c336b8e5a094eab14007c4eea9ba3755a7494e45d13527b990d6c014c475221023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05f21028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab252aeffffffffc11a1a415c7e6f164264a12fc1b2ee66424a7a8610d7f8bb975fc96677878a01000000006a473044022033c3646519579094f35f10d7dcbc443f4fac1a1346146b1d50772d88f6fa5802022057b250d9097d1cebffae67559a3cd95870ada89a1cd26470cc0d26fcbafab3720121028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab2ffffffff01000000000000000017a9142b079a4a2c1354791df4341d86ff7983426b3a9f87010000000400000002000000036c7866223335635936333654505466465738507868714833424e524c3534673154346d62523200000000

        签名交易并广播：
        命令：
        $ ./mvs-clisignmultisigtx test2 123 -b 0400000002e2ff847f7f660baae489cc219c25982b6b6c00afddc238ad92767017246917c00000000093004830450221009f620f2316ce9b5d803f7651e09971443d6cb46da47619f870148551d29ac00f022016aa63ffde9c336b8e5a094eab14007c4eea9ba3755a7494e45d13527b990d6c014c475221023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05f21028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab252aeffffffffc11a1a415c7e6f164264a12fc1b2ee66424a7a8610d7f8bb975fc96677878a01000000006a473044022033c3646519579094f35f10d7dcbc443f4fac1a1346146b1d50772d88f6fa5802022057b250d9097d1cebffae67559a3cd95870ada89a1cd26470cc0d26fcbafab3720121028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab2ffffffff01000000000000000017a9142b079a4a2c1354791df4341d86ff7983426b3a9f87010000000400000002000000036c7866223335635936333654505466465738507868714833424e524c3534673154346d62523200000000
        输出：
        0400000002e2ff847f7f660baae489cc219c25982b6b6c00afddc238ad92767017246917c000000000dc00483045022100e76e63c4f77ec03be48be1e1b5f0ca5ef344ce2d72d718b0dd958ceae74f4225022071599344cc3a03601d45ad387f2e022674e5785a2655fdbb1df2ea1c80818544014830450221009f620f2316ce9b5d803f7651e09971443d6cb46da47619f870148551d29ac00f022016aa63ffde9c336b8e5a094eab14007c4eea9ba3755a7494e45d13527b990d6c014c475221023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05f21028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab252aeffffffffc11a1a415c7e6f164264a12fc1b2ee66424a7a8610d7f8bb975fc96677878a01000000006a473044022033c3646519579094f35f10d7dcbc443f4fac1a1346146b1d50772d88f6fa5802022057b250d9097d1cebffae67559a3cd95870ada89a1cd26470cc0d26fcbafab3720121028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab2ffffffff01000000000000000017a9142b079a4a2c1354791df4341d86ff7983426b3a9f87010000000400000002000000036c7866223335635936333654505466465738507868714833424e524c3534673154346d62523200000000

        等待交易入块后查看test.mvs的迁移记录
        命令:
        $ ./mvs-cli getdid test.mvs
        输出:
        {
            "addresses" :
            [
                {
                    "address" : "35cY636TPTfFW8PxhqH3BNRL54g1T4mbR2",
                    "status" : "current"
                },
                {
                    "address" : "MP5FoYQHiEQ52pcEURkaYmuqZMnYHNAZ83",
                    "status" : "history"
                },
                {
                    "address" : "M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu",
                    "status" : "history"
                }
            ],
            "did" : "test.mvs"
        }

3.  Example: did from multi-signature address to general address

        Command:
        $ ./mvscli didchangeaddress test2 123 M9kDHsDKJj9hM8FzSmDu4xCDbo2DFzUhzj test.mvs
        Output:
        0400000002fe8ecb0c9d91147996f7cb1d2abbc2fd70253fa40a5138070167599d5125c6be000000009300483045022100a395d37e15d7e1110a53fd0f79572849511652c6a7f830a59a1f777e6d2beceb02207a9a059f935c8658595d658ea49e1a82a1a4ac501de55b522f58bd8f1f62a916014c475221023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05f21028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab252aeffffffffe2ff847f7f660baae489cc219c25982b6b6c00afddc238ad92767017246917c0010000006a47304402207f71094ebe0767c6593f8c749432b49ad981e5471af618bcf620ad6b249fb04b02204d00da73a85ed34016139772a982ba4bc003e5447fac07ffbf0163a43080dad60121023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05fffffffff0100000000000000001976a914143f0fc7d1186851be00b48bf526964b776af83b88ac010000000400000002000000036c7866224d396b444873444b4a6a39684d38467a536d447534784344626f3244467a55687a6a00000000

        Sign the transaction and broadcast:
        Command：
        $ ./mvs-clisignmultisigtx test 123 -b 0400000002fe8ecb0c9d91147996f7cb1d2abbc2fd70253fa40a5138070167599d5125c6be000000009300483045022100a395d37e15d7e1110a53fd0f79572849511652c6a7f830a59a1f777e6d2beceb02207a9a059f935c8658595d658ea49e1a82a1a4ac501de55b522f58bd8f1f62a916014c475221023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05f21028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab252aeffffffffe2ff847f7f660baae489cc219c25982b6b6c00afddc238ad92767017246917c0010000006a47304402207f71094ebe0767c6593f8c749432b49ad981e5471af618bcf620ad6b249fb04b02204d00da73a85ed34016139772a982ba4bc003e5447fac07ffbf0163a43080dad60121023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05fffffffff0100000000000000001976a914143f0fc7d1186851be00b48bf526964b776af83b88ac010000000400000002000000036c7866224d396b444873444b4a6a39684d38467a536d447534784344626f3244467a55687a6a00000000
        输出：
        0400000002fe8ecb0c9d91147996f7cb1d2abbc2fd70253fa40a5138070167599d5125c6be00000000db00483045022100a395d37e15d7e1110a53fd0f79572849511652c6a7f830a59a1f777e6d2beceb02207a9a059f935c8658595d658ea49e1a82a1a4ac501de55b522f58bd8f1f62a9160147304402202e860ee7cb122577102a9423be059a3a994c9e2804b9decdd6771c42d158f42f0220226e3e445309620184263d5dc059495ff8c379525a19636485cfb9cadbac92b7014c475221023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05f21028d6413e29808640ed5727546e62aec9a66f39465293db31eeaf2810314aa3ab252aeffffffffe2ff847f7f660baae489cc219c25982b6b6c00afddc238ad92767017246917c0010000006a47304402207f71094ebe0767c6593f8c749432b49ad981e5471af618bcf620ad6b249fb04b02204d00da73a85ed34016139772a982ba4bc003e5447fac07ffbf0163a43080dad60121023a5277232a4f9a08c83a968440c85b3a81fe43f86113342c08687bc9eb94c05fffffffff0100000000000000001976a914143f0fc7d1186851be00b48bf526964b776af83b88ac010000000400000002000000036c7866224d396b444873444b4a6a39684d38467a536d447534784344626f3244467a55687a6a00000000

        After waiting for the transaction to enter the block, check the migration record
        command of:
        $ ./mvs-cli getdid test.mvs
        output:
        {
            "addresses" :
            [
                {
                    "address" : "M9kDHsDKJj9hM8FzSmDu4xCDbo2DFzUhzj",
                    "status" : "current"
                },
                {
                    "address" : "35cY636TPTfFW8PxhqH3BNRL54g1T4mbR2",
                    "status" : "history"
                },
                {
                    "address" : "MP5FoYQHiEQ52pcEURkaYmuqZMnYHNAZ83",
                    "status" : "history"
                },
                {
                    "address" : "M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu",
                    "status" : "history"
                }
            ],
            "did" : "test.mvs"
        }

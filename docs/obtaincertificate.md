# Obtain certificate

Secondary issue certificate and domain certificate are provided after asset is issued. Naming certificate is provided by command issuecert. For issuing asset, please refer to [MST issue](https://docs.mvs.org/developers/da-issue.html).

## Obtain secondary issue certificate and domain certificate

1.  Create asset that can be secondary issued by command `createasset` If the value of option `--rate` of command `createasset` is -1 or between [1, 100], then asset that can be secondary issued is created.

        Command:
        $ ./mvs-cli createasset Alice passwd1 --symbol MVS.ALICE --volume 1000000000000 --description "Asset of Alice." --issuer Alice --decimalnumber 8 --rate -1

        Output:
        {
            "asset" :
            {
                "address" : "",
                "decimal_number" : 8,
                "description" : "Asset of Alice.",
                "is_secondaryissue" : false,
                "issuer" : "Alice",
                "maximum_supply" : 1000000000000,
                "secondaryissue_threshold" : 127,
                "status" : "unissued",
                "symbol" : "MVS.ALICE"
            }
        }

2.  Issue asset by command `issue`
    No domain certificate named MVS exists on Metavase network before Alice issues an asset named `MVS.ALICE`. So Alice got a domain certificate named MVS after she issued an asset named `MVS.ALICE`. She also got a secondary issue certificate named `MVS.ALICE` because the asset `MVS.ALICE` can be secondary issued. We can find the cert fields value of which are issue or domain from the output below.

        Command:
        $ ./mvs-cli issue Alice passwd1 MVS.ALICE

        Output:
        {
            "transaction" :
            {
                "hash" : "c88bd3914577df14063f8df7b9365d0061ee902a9ab90bf80df541ec41536321",
                "inputs" :
                [
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "previous_output" :
                        {
                            "hash" : "6ff77f00f50b18f108e6f185c99bf226a0803a0a6e58844d4043c86003de8ef3",
                            "index" : 1
                        },
                        "script" : "[ 3044022021d7739ba53653920b02bced24f1d9e0aed5d702188f6a28c2c7371883fc9b0b02204fe7bc03309331b0355cf79600691a63b5ee8f1c64cd8db01321db041614851b01 ] [ 038d7048a4e640a0e0a27ef85d2a7e5b339834cd565ada0d6ea042127732fa105e ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "previous_output" :
                        {
                            "hash" : "19dad273d07090648279817e8dcbce8dc06c9815ee94fa798d8e779cf66a9076",
                            "index" : 0
                        },
                        "script" : "[ 304402205e6cb2bd7e9746bc9181ec66043a3244d9f502f03174a384d53853da44f2d2eb022056e19b54d01ae8ad164ca6e856ab7ed12c8c42081c0451cc66c990c08a783be101 ] [ 038d7048a4e640a0e0a27ef85d2a7e5b339834cd565ada0d6ea042127732fa105e ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "previous_output" :
                        {
                            "hash" : "c42114b2626d9a6e82888deade68c82500e1e55494318c2c3eed7f0a065895e9",
                            "index" : 0
                        },
                        "script" : "[ 304502210091b393ed73b59d89a37a7d8c2d0145f5f010a3ca29897b9ed0283782cebba7690220489e6564f17f62a9ec5b1f642be030395318f405ffeb4023c08282360070301b01 ] [ 038d7048a4e640a0e0a27ef85d2a7e5b339834cd565ada0d6ea042127732fa105e ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "previous_output" :
                        {
                            "hash" : "cb62c51992f141490ba8934e422a47f5e8d11cf92cbfedbd99bf4247865d6579",
                            "index" : 0
                        },
                        "script" : "[ 304402200a152c449de59abbd53bd54cd8164b2b2ede152e8350358b4aa1014f733b75a902200bc64b0edfd4c5cd3667d9b416f4361ea6cf24649aebe06e6d3e93b2fa0b2ce301 ] [ 038d7048a4e640a0e0a27ef85d2a7e5b339834cd565ada0d6ea042127732fa105e ]",
                        "sequence" : 4294967295
                    }
                ],
                "lock_time" : "0",
                "outputs" :
                [
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "attachment" :
                        {
                            "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                            "decimal_number" : 8,
                            "description" : "Asset of Alice.",
                            "from_did" : "",
                            "is_secondaryissue" : false,
                            "issuer" : "Alice",
                            "quantity" : 1000000000000,
                            "secondaryissue_threshold" : 127,
                            "symbol" : "MVS.ALICE",
                            "to_did" : "Alice",
                            "type" : "asset-issue"
                        },
                        "index" : 0,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ 95c9a5e647870bbc535d83a3c394ef40d298aa46 ] equalverify checksig",
                        "value" : 0
                    },
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "attachment" :
                        {
                            "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                            "cert" : "issue",
                            "from_did" : "",
                            "owner" : "Alice",
                            "symbol" : "MVS.ALICE",
                            "to_did" : "Alice",
                            "type" : "asset-cert"
                        },
                        "index" : 1,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ 95c9a5e647870bbc535d83a3c394ef40d298aa46 ] equalverify checksig",
                        "value" : 0
                    },
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "attachment" :
                        {
                            "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                            "cert" : "domain",
                            "from_did" : "",
                            "owner" : "Alice",
                            "symbol" : "MVS",
                            "to_did" : "Alice",
                            "type" : "asset-cert"
                        },
                        "index" : 2,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ 95c9a5e647870bbc535d83a3c394ef40d298aa46 ] equalverify checksig",
                        "value" : 0
                    },
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "attachment" :
                        {
                            "type" : "etp"
                        },
                        "index" : 3,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ 95c9a5e647870bbc535d83a3c394ef40d298aa46 ] equalverify checksig",
                        "value" : 100000000
                    }
                ],
                "version" : "4"
            }
        }

## Obtain naming certificate

The owner of domain certificate can issue the naming certificate whose domain name is the name of domain certificate by command `issuecert`.

`issuecert` needs the following paramenters: `account_name`, `account_passwd`, `to_did`, `cert_symbol`, `cert_type`. Only naming certificate can be issued now.

For example, Alice owns a domain certificate named MVS then she can issue a naming certificate named `MVS.BOB` to did Alice which belongs to she too.

    Command:
    $ ./mvs-cli issuecert Alice passwd1 Alice MVS.BOB naming

    Output:
    {
        "transaction" :
        {
            "hash" : "578c23781ab4251c02f2987f5ad0cbeb8ed526546877364efe853e5a345549d9",
            "inputs" :
            [
                {
                    "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                    "previous_output" :
                    {
                        "hash" : "c88bd3914577df14063f8df7b9365d0061ee902a9ab90bf80df541ec41536321",
                        "index" : 3
                    },
                    "script" : "[ 3045022100fef8cf721e972b256241aa983c5ce123be4ce0d50bfaf5c8696e5c17486e133f02203147741b4868e34e4f8a3b32e8b7ef1605582950e80c0cd04eee584989507cff01 ] [ 038d7048a4e640a0e0a27ef85d2a7e5b339834cd565ada0d6ea042127732fa105e ]",
                    "sequence" : 4294967295
                },
                {
                    "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                    "previous_output" :
                    {
                        "hash" : "c88bd3914577df14063f8df7b9365d0061ee902a9ab90bf80df541ec41536321",
                        "index" : 2
                    },
                    "script" : "[ 3045022100959f7b4e694610c1078b310dbf5ea1cf710175e1349b469239fb79e81ca974f502202bf495d589a5b9ef0341689a8c88bb739762b538cf472422216e0dfc33f51f8101 ] [ 038d7048a4e640a0e0a27ef85d2a7e5b339834cd565ada0d6ea042127732fa105e ]",
                    "sequence" : 4294967295
                }
            ],
            "lock_time" : "0",
            "outputs" :
            [
                {
                    "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                    "attachment" :
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "cert" : "naming",
                        "from_did" : "",
                        "owner" : "Alice",
                        "symbol" : "MVS.BOB",
                        "to_did" : "Alice",
                        "type" : "asset-cert"
                    },
                    "index" : 0,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 95c9a5e647870bbc535d83a3c394ef40d298aa46 ] equalverify checksig",
                    "value" : 0
                },
                {
                    "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                    "attachment" :
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "cert" : "domain",
                        "from_did" : "",
                        "owner" : "Alice",
                        "symbol" : "MVS",
                        "to_did" : "Alice",
                        "type" : "asset-cert"
                    },
                    "index" : 1,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 95c9a5e647870bbc535d83a3c394ef40d298aa46 ] equalverify checksig",
                    "value" : 0
                },
                {
                    "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                    "attachment" :
                    {
                        "type" : "etp"
                    },
                    "index" : 2,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 95c9a5e647870bbc535d83a3c394ef40d298aa46 ] equalverify checksig",
                    "value" : 99990000
                }
            ],
            "version" : "4"
        }
    }

## Transfer cert

Certificates can be transfered to other DIDs which can be owned by other account by command `transfercert`.

`transfercert` needs the following paramenters: `account_name`, `account_passwd`, `to_did`, `cert_symbol`, `cert_type`. This command suports multi-sign, that means certificates can be transferd from or to DIDs which is multi-signed.

In the previous example, Alice issued a naming certificate named `MVS.BOB`. Now Alice can transfer it to DID Bob which belongs to account Bob.

    Command: $ ./mvs-cli transfercert Alice passwd1 Bob MVS.BOB naming

        Output:
        {
            "transaction" :
            {
                "hash" : "0a985f55345cd5ca81df08c263033c34b8895bf18db6435e8b2509ebbe9f4b0f",
                "inputs" :
                [
                    {
                        "address" : "MNz5WH5CH1T44hTpanbG1v1NBjcZXf4je4",
                        "previous_output" :
                        {
                            "hash" : "98f70aba9c690700dd66ec0c8fce2c56c22043d1c20ff76f164170cc10050c70",
                            "index" : 0
                        },
                        "script" : "[ 3045022100a0527a44333aa92ed469b34431eff09d31a7eaaf20a7b86b09cd395d69f74c0e02203b28dc32d9db29ee1d398021a0652be0a2b4486b8137471efb29b77a215aa11701 ] [ 02eee915ccdb35cc35583a3ad58be24fe914d754d00cd75641f56cc90fc305e307 ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                        "previous_output" :
                        {
                            "hash" : "578c23781ab4251c02f2987f5ad0cbeb8ed526546877364efe853e5a345549d9",
                            "index" : 0
                        },
                        "script" : "[ 3045022100bada970681995f64fdd8716075f3b4ee7116d63376a5811ed1d897c99283eea3022027cd6761027155b7f892ad4d4944019fdb75ee3b15761e7e9f58738ed0010c0e01 ] [ 038d7048a4e640a0e0a27ef85d2a7e5b339834cd565ada0d6ea042127732fa105e ]",
                        "sequence" : 4294967295
                    }
                ],
                "lock_time" : "0",
                "outputs" :
                [
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "attachment" :
                        {
                            "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                            "cert" : "naming",
                            "from_did" : "",
                            "owner" : "Bob",
                            "symbol" : "MVS.BOB",
                            "to_did" : "Bob",
                            "type" : "asset-cert"
                        },
                        "index" : 0,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ ee51cd6e869195dca48ede01f40a18c275322fbd ] equalverify checksig",
                        "value" : 0
                    },
                    {
                        "address" : "MNz5WH5CH1T44hTpanbG1v1NBjcZXf4je4",
                        "attachment" :
                        {
                            "type" : "etp"
                        },
                        "index" : 1,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ a57805573daf3760779ff5dfc820ba5728e462d2 ] equalverify checksig",
                        "value" : 299990000
                    }
                ],
                "version" : "4"
            }
        }

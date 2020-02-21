# Use Certificate

Certificates are usually used implicitly. For example, domain certificate or naming certificate may be used while issuing asset by command `issue`; secondary issue certificate is used while secondary issuing asset by command `secondaryissue`; domain certificate is used while issuing naming certificate by command `issuecert`. Certificates can be used explicitly by command `transfercert` too.

## Using naming certificate to create asset

In the previous example, Bob got a naming certificate named `MVS.BOB` from Alice. Now Bob can issue an asset named `MVS.BOB`.

1.  Create asset

        $ ./mvs-cli createasset Bob passwd1 --symbol MVS.BOB --volume 1000000000000 --description "Asset of BOB." --issuer Bob --decimalnumber 8 --rate -1
        {
            "asset" :
            {
                "address" : "",
                "decimal_number" : 8,
                "description" : "Asset of BOB.",
                "is_secondaryissue" : false,
                "issuer" : "Bob",
                "maximum_supply" : 1000000000000,
                "secondaryissue_threshold" : 127,
                "status" : "unissued",
                "symbol" : "MVS.BOB"
            }
        }

2.  Issue asset

        $ ./mvs-cli issue Bob passwd1 MVS.BOB
        {
            "transaction" :
            {
                "hash" : "3e6084732f35dac309f2243ef890e9455ccf930f1f54be386666e52356961234",
                "inputs" :
                [
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "previous_output" :
                        {
                            "hash" : "0a985f55345cd5ca81df08c263033c34b8895bf18db6435e8b2509ebbe9f4b0f",
                            "index" : 0
                        },
                        "script" : "[ 3045022100b79b10adf94b3cf7dfe33d45e6b65598c3008b348d87363cee429d24f9a0bd74022077ab16d574b0d3c118058316b950c27f1660c7ef2ece3e4bdbdd6b6bf2b7004701 ] [ 0218feb8b4eb5d83d5ca93116a09c1b16f9587db78af950a06c15c1c82e81866df ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "previous_output" :
                        {
                            "hash" : "a0b321d1ce636644fa51f78f3a4a2ea66aa52b623a4759ae5b61b9f57ea4b647",
                            "index" : 1
                        },
                        "script" : "[ 3045022100ec6ff9fb6cdd7fb11883d05c43bbbb767111b4efbad2b96b5bfb456e470df54f0220531100981698ff204b76ffc53399de1bf33fbaf4dbd0ca666f57ceaf75bcfbf001 ] [ 0218feb8b4eb5d83d5ca93116a09c1b16f9587db78af950a06c15c1c82e81866df ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "previous_output" :
                        {
                            "hash" : "5be8df2c2e3d2a7ecd6f1963cba046a78a4c959b6eb4d94a8396602d23c2a44a",
                            "index" : 0
                        },
                        "script" : "[ 3045022100e2d0c79673293c971b146fb3974ee5d36aa1c1fd8a24a785fe1577d634676df602203f048e25dd9c2920a29ecf2ea60774a8a1f6429b6c0ba1bc712d54757b9e994801 ] [ 0218feb8b4eb5d83d5ca93116a09c1b16f9587db78af950a06c15c1c82e81866df ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "previous_output" :
                        {
                            "hash" : "91290adcfae5b490e0077ea6f2ba4484b4195f187a823023cc0bf829cae66147",
                            "index" : 0
                        },
                        "script" : "[ 30440220790e9ac92450ae4bd18420d5d3bb94cdd85f50c30ec54dace549169deb500a7b0220384038a8fe308a1330af337d3f3e3404e62d147b1b00f30a4c4a304a205f2e7901 ] [ 0218feb8b4eb5d83d5ca93116a09c1b16f9587db78af950a06c15c1c82e81866df ]",
                        "sequence" : 4294967295
                    },
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "previous_output" :
                        {
                            "hash" : "e4df769a43a7fb28aa29c2c9809014c04335afd690ab48f5359bcf4f70f94e9a",
                            "index" : 0
                        },
                        "script" : "[ 3045022100f1eb735631261c4e7b1e7591f09d999dbcda13efec29f8e350c5ceb3772f7769022077168d79740e4ee1f0af9b5f733855cd70091b9564562d57e571ddcace1f139101 ] [ 0218feb8b4eb5d83d5ca93116a09c1b16f9587db78af950a06c15c1c82e81866df ]",
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
                            "decimal_number" : 8,
                            "description" : "Asset of BOB.",
                            "from_did" : "",
                            "is_secondaryissue" : false,
                            "issuer" : "Bob",
                            "quantity" : 1000000000000,
                            "secondaryissue_threshold" : 127,
                            "symbol" : "MVS.BOB",
                            "to_did" : "Bob",
                            "type" : "asset-issue"
                        },
                        "index" : 0,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ ee51cd6e869195dca48ede01f40a18c275322fbd ] equalverify checksig",
                        "value" : 0
                    },
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "attachment" :
                        {
                            "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                            "cert" : "issue",
                            "from_did" : "",
                            "owner" : "Bob",
                            "symbol" : "MVS.BOB",
                            "to_did" : "Bob",
                            "type" : "asset-cert"
                        },
                        "index" : 1,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ ee51cd6e869195dca48ede01f40a18c275322fbd ] equalverify checksig",
                        "value" : 0
                    },
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
                        "index" : 2,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ ee51cd6e869195dca48ede01f40a18c275322fbd ] equalverify checksig",
                        "value" : 0
                    },
                    {
                        "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                        "attachment" :
                        {
                            "type" : "etp"
                        },
                        "index" : 3,
                        "locked_height_range" : 0,
                        "script" : "dup hash160 [ ee51cd6e869195dca48ede01f40a18c275322fbd ] equalverify checksig",
                        "value" : 100000000
                    }
                ],
                "version" : "4"
            }
        }

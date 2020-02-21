# DID Query

### View a list of digital identities

Registered digital identities can be viewed through listdids

    Command:
    $ listdids
    Usage: mvs-cli listdids [-h] [ACCOUNTNAME] [ACCOUNTAUTH]

    Info: list whole network DIDs in details.

    Options (named):

    -h [--help]          Get a description and instructions for this command.

    Arguments (positional):

    ACCOUNTNAME          Account name required.
    ACCOUNTAUTH          Account password(authorization) required.

1. Example: View all did registered on the chain


        Command:
        $ ./mvs-cli listdids
        输出：
        {
                "dids" :
                [
                    {
                            "address" : "MN3UNt5FbUbpsYtW6UfhcieykUb8rXKP5g",
                            "status" : "registered",
                            "symbol" : "Alice.DIID"
                    },
                    {
                            "address" : "MLixg7rxKmtPj9DT9wPKSy6WkJkoUDWUSv",
                            "status" : "registered",
                            "symbol" : "Alice.DIID2"
                    },
                    {
                            "address" : "M9ZTG5ed4Tbsir7rD1JYYFVaaWnYmBxHs7",
                            "status" : "registered",
                            "symbol" : "Bob.DIID"
                    },
                    {
                            "address" : "MAhmaLbfLFFMQF88xWAqibDaPfQfYqpv8Y",
                            "status" : "registered",
                            "symbol" : "Cindy.DIID"
                    }
                ]
        }

2.  Example: View all did registered for the current account

        Command:
        $ ./mvs-cli listdids Alice 123
        输出：
        {
                "dids" :
                [
                    {
                            "address" : "MN3UNt5FbUbpsYtW6UfhcieykUb8rXKP5g",
                            "status" : "registered",
                            "symbol" : "Alice.DIID"
                    },
                    {
                            "address" : "MLixg7rxKmtPj9DT9wPKSy6WkJkoUDWUSv",
                            "status" : "registered",
                            "symbol" : "Alice.DIID2"
                    }
                ]
        }

### View historical addresses

Every digital identity will be recorded on the chain from registration to transfer, you can view the migration record of did

        View all digital identity list
        Commands：
        $ getdid
        Usage: mvs-cli getdid [-h] [DID/ADDRESS]

        Info: getdid

        Options (named):

        -h [--help]          Get a description and instructions for this command.

        Arguments (positional):

        DID/ADDRESS          Did symbol or standard address; If no input
                            parameters, then display whole network DIDs.
        Rule:
        parameter is ADDRESS, the historical address of did corresponding to ADDRESS is displayed

1.  Example: View all did registered on the chain

        Command:
        $ ./mvs-cli getdid
        Output:
        {
                "dids" :
                [
                    "Alice.DIID",
                    "Alice.DIID2",
                    "Bob.DIID",
                    "Cindy.DIID",
                ]
        }

2.  Example: View the historical address of did migration


        Command:
        $ ./mvs-cli getdid test.mvs or ./mvs-cli getdid M9kDHsDKJj9hM8FzSmDu4xCDbo2DFzUhzj
        Ouput:
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

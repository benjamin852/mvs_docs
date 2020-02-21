# Query certificates

Follow commands: `listassets`, `getasset`, `getaccountasset` and `getaddressasset`, have an option `--cert` to query information of certificates。

The information of certificate have four fields：

1. address: address of certificate.
2. cert: type name of certificate. “domain”, “issue”, “naming” are supported.
3. owner: DID who owned the certificate.
4. symbol: name of certificate.

## getasset

Query the names of certificates on Metaverse network or display the information of specified certificate.

    $ ./mvs-cli getasset
    {
        "assets" :
        [
            "MVS",
            "MVS.ALICE",
            "MVS.BOB",
        ]
    }

    $ ./mvs-cli getasset --cert MVS.BOB
    {
        "assetcerts" :
        [
            {
                "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                "cert" : "naming",
                "owner" : "Bob",
                "symbol" : "MVS.BOB"
            }
        ]
    }

## listasset

Query the information of certificates on Metaverse network or the information of certificates owned by the specified account.

    $ ./mvs-cli listassets --cert
    {
        "assetcerts" :
        [
            {
                "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                "cert" : "domain",
                "owner" : "Alice",
                "symbol" : "MVS"
            },
            {
                "address" : "MMZAUmJke7f1FEY67dAHUYfmfh2wWC4vFL",
                "cert" : "issue",
                "owner" : "Alice",
                "symbol" : "MVS.Alice"
            },
            {
                "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                "cert" : "issue",
                "owner" : "Bob",
                "symbol" : "MVS.BOB"
            },
            {
                "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                "cert" : "naming",
                "owner" : "Bob",
                "symbol" : "MVS.BOB"
            },
        ]
    }

    ./mvs-cli listassets --cert Bob passwd1
    {
        "assetcerts" :
        [
            {
                "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                "cert" : "naming",
                "owner" : "Bob",
                "symbol" : "MVS.BOB"
            }

        ]
    }

## getaccountasset

Query the information of certificates owned by the specified account.

    $ ./mvs-cli getaccountasset Bob passwd1 --cert
    {
        "assetcerts" :
        [
            {
                "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                "cert" : "naming",
                "owner" : "Bob",
                "symbol" : "MVS.BOB"
            }
        ]
    }

    $ ./mvs-cli getaccountasset Bob passwd1 MVS.BOB --cert
    {
        "assetcerts" :
        [
            {
                "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                "cert" : "naming",
                "owner" : "Bob",
                "symbol" : "MVS.BOB"
            }
        ]
    }

## getaddressasset

Query the information of certificates at the specified address.

    $ ./mvs-cli getaddressasset MD9i7CXfRssTXr3DTtsn22KFyWwaxRLu4f --cert
    {
        "assetcerts" :
        [
            {
                "address" : "MVdH3pZrjPqgvg51pYfr7ct1hEqL4R25fz",
                "cert" : "naming",
                "owner" : "Bob",
                "symbol" : "MVS.BOB"
            }
        ]
    }

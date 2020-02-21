# Digital Identity (Avatar) Usage

### registered

Before registering a digital identity, you must have an already created account. You need to pay 1 etp to pay the commission fee at the destination address. After the registration is successfully integrated into the block, you can use it to send transactions.
Registering a digital identity requires parameters: account, account password, Destination address, digital identity sign.

    Command:
    $ registerdid
    Usage: mvs-cli registerdid [-h] [--fee value] ACCOUNTNAME ACCOUNTAUTH
    ADDRESS SYMBOL

    Info: registerdid

    Options (named):

    -H [- Help ] Description A and the Get Instructions for the this Command .
    -f [--fee] Defaults to TX of The Fee of ETP. 1..

    Arguments (positional):

    ACCOUNTNAME Account name required.
    ACCOUNTAUTH Account password (authorization) required.
    ADDRESS The address will be bound to, can change to other
                        addresses later.
    SYMBOL The symbol of global unique MVS Digital Identity
                        Destination / Index, supports
                        alphabets / numbers / ("@" , ".", "_",
                        "-"), Case -sensitive, maximum length is 64.


    Rules:
    ADDRESS belongs to the current account;
    SYMBOL is composed of letters, numbers and special characters ( "@" , "." , "_" , "-" ), Is case sensitive, and the maximum length cannot exceed 64;
    SYMBOL cannot be a valid address and Cannot be repeated on the chain;
    SYMBOL cannot be the keyword "BLACKHOLE" . "BLACKHOLE" is not case sensitive, that is, "BLACKHOLE" , "blockhole" , "BlockHole" and other forms are all invalid SYMBOL;
    SYMBOL cannot be a politically sensitive word;
    registration did need at least 1 etp

Example: Use the account 'test' to register the digital identity with the name 'test.mvs' and bind it to a valid address 'M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu'

    $ ./mvs-cli registerdid test 123 M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu test.mvs

    {
        "transaction" :
        {
            "hash" : "4d5ae5bfdd89d30a771680cd3080478e741ff1bea65b4903ea42160952c0c9e8",
            "inputs" :
            [
                {
                    "address" : "M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu",
                    "previous_output" :
                    {
                        "hash" : "a7db09dcf9e8d9341f8343a6f1edfb2fd1fdf350ccef8f3517b446eeb2d73076",
                        "index" : 0
                    },
                    "script" : "[ 304402201c9b9706b3e198e9de8887c94c6e7f1192a65cb1fa15318b409f6d4fc4952f9a0220306d2f5fcdf2e1e32861399dc55b7c81a1cedc7790d2ff8a73a8bb3f9bac5fde01 ] [ 035f572a164ec0e7d8f1935e357d86c6441152bed7251389a1c66174ae890dad90 ]",
                    "sequence" : 4294967295
                }
            ],
            "lock_time" : "0",
            "outputs" :
            [
                {
                    "address" : "M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu",
                    "attachment" :
                    {
                        "address" : "M9L3ipy3Hcf6kdvknU3mH7mwH9ER3uCziu",
                        "symbol" : "test.mvs",
                        "type" : "did-register"
                    },
                    "index" : 0,
                    "locked_height_range" : 0,
                    "script" : "dup hash160 [ 0fad171975f1100309022c83c7b9dca0a8f8e6b8 ] equalverify checksig",
                    "value" : 0
                }
            ],
            "version" : "4"
        }
    }

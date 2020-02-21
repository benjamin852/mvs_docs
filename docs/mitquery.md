# Query MIT

## Precondition

This is mainly about register MIT command line operation.

First, you need an account and a did. You can use `mvs-cli getnewaccount accountname password` and `mvs-cli issuedid accountname password address did` to generate a new account and a new did.

For convenience, I’ll uniformly use Alice as account name, passwd1 as password, Alice as did, and use testing addresses in the following examples. When you refer to the following examples, please change to your account name, password and did, and pay attention to the correct addresses.

With an account, if you want to issue or send an asset, you have to make sure that there is enough ETP in the account to pay fees. You can use `mvs-cli getbalance account_name password` to get the total balance of the account. You can also use `mvs-cli listbalances account_name password` to list the balance of each address in the account.

You can use help to get the help information of each command. For eaxmple, use `mvs-cli help registermit` or `mvs-cli registermit -h` to get the help information of `registermit`

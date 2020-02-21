# MST Certificate

## Precondition

You need an account and a did. You can use `mvs-cli getnewaccount accountname password` and `mvs-cli issuedid accountname password address did` to generate a new account and a new did.

For convenience, I’ll uniformly use Alice as account name, passwd1 as password, Alice as did, and use testing addresses in the following examples. When you refer to the following examples, please change to your account name, password and did, and pay attention to the correct addresses.

With an account, if you want to issue or send an asset, you have to make sure that there is enough ETP in the account to pay fees. You can use `mvs-cli getbalance account_name password` to get the total balance of the account. You can also use `mvs-cli listbalances account_name password` to list the balance of each address in the account.

You can use help to get the help information of each command. For eaxmple, use `mvs-cli help createasset` or `mvs-cli createasset -h` to get the help information of createasset command.

## What is MST Certificate?

The asset certificate is a certificate of an asset’s interest. It is unique and can be transferred between DIDs. Secondary issue certificate, domain certificate and naming certificate are supported now. Assets or certificate can only be issued if user has the appropriate certificate.

## Type of certificate

Secondary issue certificate, domain certificate and naming certificate are supported now：

<b>issue:</b> Secondary issue certificate. Asset can only be secondary issued if user has a secondary issue certificate with the same name as the asset. This certificate is automatically issued to the issuer when issuing assets that can be secondary issued. Related commands: createasset, issue, secondaryissue.

<b>domain:</b> Domain certificate. The domain certificate is automatically provided at the asset creation stage and is available on the first-issue first-served basis. For example, if you own the domain MVS, only you can create an asset whose name starts with MVS. Related commands: createasset, issue.

<b>naming:</b> Naming certificate. The owner of domain certificate can create the naming certificate that can be transferred to others, for them to issue the asset with the same name as the naming certificate. Related commands: issuecert, transfercert.

Notes: Issuing a asset whose name starts with a dot . would not generate any certificate.

# MVS Wallet Upgrade Manual

1.  <b>Download the installation package from Metaverse’s official website
    URL: [https://mvs.org/wallet.html](https://mvs.org/wallet.html)</b>

2.  <b>Read the release notes
    URL: https://docs.mvs.org/news/</b>

3.  <b>Exit the running old wallet (ignore this step if no one is running)</b>

4.  <b>Backup account and database</b>

    4.1 Backup account
    <b>CAUTION: PLEASE BACKUP YOUR ACCOUNT’s MNEMONIC-PHRASE OF MASTER-KEY AT FIRST.</b>
    Ref. [How To Backup And Import Account](https://docs.mvs.org/docs/backup-account.html#Backup-and-import-account)

    4.2 Backup database
    Open or enter the following directory:

        # Windows: Explorer
        `%HOMEPATH%\AppData\Roaming\Metaverse`

        # Mac-OSX: Finder => go to folder
        `~/Library/Application Support/Metaverse`

        # Linux(unix-like):
        `~/.metaverse`

Copy and paste the whole mainnet directory as a backup.

In order to save disk space, you can only backup the account related tables whose table name have prefix account\_. Ref. How To Backup And Import Account Related Tables

5 <b>Install latest version of Metaverse full node wallet</b>

You can re-install the new wallet by overlay installation,
or uninstall the old wallet and then install the new wallet.

6 <b>Startup the new wallet</b>

In the intial startup of the new wallet, do not exit soon after startup.
Please give 10 minutes or so for the wallet to init or upgrade the database.
When the block is beginning to synchronize, you can exit whenever you want.

7 <b>Check the running status of the wallet</b>

Mainly check if the wallet is running, and check if the blocks is synchronizing normally.

8 <b>Recover and retry when failed (ignore this step if has no problem in the previous steps)</b>

Just replace the mainet database with the backup one, and retry to run the new wallet.
If still has problem, please contact the MVS technical support.

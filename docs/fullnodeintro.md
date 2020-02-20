# Metaverse full node introduction

Full nodes are nodes that store the entire Metaverse blockchain and are connected in a P2P network architecture. In the blockchain network, all full nodes are treated as equals, and serve as both clients and servers.

# The MVS full node consists of two programs and a graphical interface:

• `mvsd`: The core wallet program, similar to Bitcoin’s bitcoind;
• `mvs-cli`: a command line interface, similar to Bitcoin’s bitcoin-cli
• `mvs-htmls`: a browser-based graphical user interface built with AngularJS. This GUI may not be necessary for developers.

# MVS full node wallet - function list

mvsd&mvs-cli Broswer GUI
Graphic Interfac √
Command Line Interface √ √
Create Account √ √
Import and Export Mnemonics √ √
Create Address √ √
Batch Generation Address √ √
ETP Transfer √ √
ETP Deposit (Coinlock) √ √
Show All Addresse √ √
Show All Assets √ √
Create Asset (Not broadcast) √ √
Delete Asset (Not broadcast) √
Issue Asset √ √
Transfer Asset √ √
Create a multi-party signature transactio √ √
Offline signature √
List the transaction details of the designated assets of the wallet √ √
mining √

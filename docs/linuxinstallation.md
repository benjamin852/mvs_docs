# Installation for Linux

Please download the latest wallet installation package from Metaverse’s official [https://mvs.org/wallet.html](https://mvs.org/wallet.html). The wallet is now support Linux 64 bit system. At least 10 GB of free disk space is required for the installation.

<b>Take version v0.8.4 as an example.</b>

## Download and unzip

Download standard versions

`# for tarballs`
`wget [https://s3-us-west-1.amazonaws.com/wallet.mvs.org/download/mvs-linux-x86_64-v0.8.4.tar.gz`
`tar -zxf mvs-linux-x86_64-v0.8.4.tar.gz`

## Install standard versions

`cd mvs-linux-x86_64-v0.8.4`
`./mvs-install.sh`

## Run

`# run 'mvsd', waiting for block synchronized. Get lastes block height from <https://explorer.mvs.org>.`
`# option '-d' run as daemon mode`
`mvsd -d`

`# Get helps from mvsd`
`mvsd --help`

`# Get helps from mvs-cli`
`mvs-cli help`

## Download database package to reduces the time required for initial block syncing

Download database package
`\$ wget http://newmetaverse.org/mvs-download/block-data/mvs-block-data-for-linux.tar.gz`

`$ tar -xzvf mvs-block-data-for-linux.tar.gz`

`# The default path of database folder is ~/.metaverse/mainnet`
`# Please specify PATH_TO_BLOCK_DATA to your customized database folder.`
`# ./copy-block-data.sh PATH_TO_BLOCK_DATA`
`\$ ./copy-block-data.sh`

## Get started

1. Run mvs-cli in terminal. More mvs-cli usage information please see [mvs-cli usage](https://docs.mvs.org/docs/command-line.html#mvs-cli-usage)
2. Access wallet on browser. Default URL is `127.0.0.1:8820` (specified by `mongoose_listen` vaule in `mvs.conf`). More configuration information please see [Config File](https://docs.mvs.org/docs/config-file.html)

# PoS and MST Mining

## Download & Install v0.9.0 MPC1

Please refer to [Download wallet](https://mvs.org/wallet.html) to download and install the latest wallet.

## PoS Mining

It is easy to mine PoS block for avatar that has many UTXOs which has at least 1000 ETP.
Please follow the steps to start PoS mining:

1. Register a avatar.
2. Lock at least 1000 ETP by call lock with the avatar. The minimum lock height range is 100000.
3. The avatar should holds at least one UTXO which has at least 1000 ETP and over 1000 height maturity.
4. `startmining` with option `-c pos`.

## Operations on fullnode wallet

![Full Node Operations](./img/fullnode_ops.png)

## MST Mining

#### MST Issuer

MST issuer should specify the MST mining subsidy parameters(`--subsidy`) when he issue a MST if he want the MST to be mined.

The format of `--subsidy` parameter is `initial:unit32,interval:unit32,base:float`.

And MST mining reward is calculated by：`initial \* pow(base, (block_height/interval))`.

#### Example

issue:
`./mvs-cli issue testacc testacc MST.MST.TEST -s "initial:300000000,interval:500000,base:0.95"`

MST mining reward = 300000000 \* pow(0.95, (Current block height - Height when MST issued) / 500000).

#### Operations on Full Node Wallet

[PIC17]

#### Miner

Miner `startmining` with option `--symbol` and the symbol of MST to be mined.

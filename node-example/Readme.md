# Run a BCC Validator
## Setting up a node
1. Git clone https://github.com/blokistachain/CoinNetwork.git

2. Copy source form node-example to root folder
```
cp -r CoinNetwork/node-example/BCC  /root/
```
3. Create an Account

```
cd /root/BCC
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake BCC coin, all you should do is sending your BCC coin to the BCC Consensus contract address over the BCC network from the validator address.
    The BCC Consensus contract address: 0x510f460A14420788785582380b580187C57D9a9D
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to BCC and send the BCC coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /BCC/nodes/validator/keys/BCC/UTC--xxxx
    /BCC/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.

# Run a GOLDX Validator
## Setting up a node
1. Git clone https://github.com/fkt20/GOLDXNetwork.git

2. Copy source form node-example to root folder
```
cp -r GOLDXNetwork/node-example/GOLDX  /root/
```
3. Create an Account

```
cd /root/GOLDX
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

    To stake GOLDX coin, all you should do is sending your GOLDX coin to the GOLDX Consensus contract address over the GOLDX network from the validator address.
    The GOLDX Consensus contract address: 0x6FFB7F1BAfec6D1cB3993928f8D1ce9f7835F6a1
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to GOLDX and send the GOLDX coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /GOLDX/nodes/validator/keys/GOLDX/UTC--xxxx
    /GOLDX/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.

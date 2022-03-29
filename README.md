# AEC

create AEC TOKE base in ERC721

# 初始化环境
    1.go
    2.配置geth环境变量
    3.私链配置：

    {
    "config": {
    "chainId": 15,
    "homesteadBlock": 0,
    "eip150Block": 0,
    "eip150Hash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "eip155Block": 0,
    "eip158Block": 0,
    "byzantiumBlock": 0,
    "constantinopleBlock": 0,
    "petersburgBlock": 0,
    "istanbulBlock": 0,
    "ethash": {}
    },
    "nonce": "0x0",
    "timestamp": "0x5ddf8f3e",
    "extraData": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "gasLimit": "0x47b760",
    "difficulty": "0x00002",
    "mixHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "coinbase": "0x0000000000000000000000000000000000000000",
    "alloc": { },
    "number": "0x0",
    "gasUsed": "0x0",
    "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000"
    }

# 开始挖矿

    1.配置初始化文件
    2.geth --datadir . init genesis.json 
    3.启动私链 
        geth --allow-insecure-unlock --identity "Amence" --http --http.addr 0.0.0.0 --http.port=8545 --http.vhosts="*" --http.api='personal,eth,net,web3,admin,txpool,miner' --ws --ws.addr=0.0.0.0 --ws.port=8546 --ws.api='eth,net,web3' --ws.origins="*"  --datadir ./data --port "30303"  --networkid 10 console 2>log

# 查询账户

    eth.accounts

# 查询余额

    eth.getBalance("0x9fF20867B0432ad3A4e6d2f7Caf6D7da6E6154ce")

# 新建账户

    > personal.newAccount()
    Passphrase:
    Repeat passphrase:
    "0xf5d90b1884554843ab677b6fdaf4366e7cc39123"

# 解锁账户

    personal.unlockAccount(eth.accounts[0])

# 开始挖矿

    miner.start(1)
    eth.getBalance(eth.accounts[0])

# 转账

    eth.sendTransaction({from:eth.accounts[0],to:eth.accounts[1],value:1000})

# 查看交易

    eth.getTransaction("0x3cd2617120473bcc478eaf9c18f7a9f160e950e8496096213e7794001b4ad331")

# 查看区块

    eth.getBlock(1499)

# 倒入私钥
    1.将私钥写入文件pk中
    geth account import --datadir ./data pk

# 部署合约



# 区块链Demo程序使用手册

该区块链Demo程序是一个简单的区块链实现，用于展示区块链的基本概念和功能。它模拟了一个简化的区块链网络，包括创建区块链、添加交易、挖矿和查看余额等操作。 它包括以下文件：

- main.py：程序的主入口，用于演示区块链的创建、交易和挖矿等操作。
- BlockChain.py：区块链类的定义和实现，包括添加区块、验证区块、获取余额等功能。
- Block.py：区块类的定义和实现，包括计算区块哈希值、计算交易列表的默克尔根哈希值等功能。
- Miner.py：矿工类的定义和实现，用于挖矿和获得挖矿奖励。
- Transaction.py：交易类的定义和实现，包括发送者、接收者和交易金额等属性。

## 环境要求

- Python 3.x

## 安装和运行

1. 安装Python 3.x环境。

2. 克隆或下载该区块链Demo程序的代码库。

   ```
   git clone https://github.com/PGone-AKA/BlockChainDemo.git
   ```

3. 进入代码库所在的目录。

   ```
   cd BlockChainDemo
   ```
4. 运行Demo程序。

   ```
   python main.py
   ```

5. 您将看到区块链Demo程序的输出，包括创建区块链、添加交易、挖矿和查看余额等操作的结果。

   > 注意：该Demo程序仅用于展示区块链的基本概念和功能，并不具备真实的区块链网络和加密算法等特性。
   ```
   挖到区块:0000045a184590e908cd7fb3103b6743c0e331a985a019d776489157baece085, 耗时: 2.7364550000000003秒
   恭喜你获得出块奖励$1000!
   用户名：xuxiaoyang
   账户：080127b91bd484fa0caea965441d01e8f76b5738b48cc16b4ad5ec10eab94135 
   余额：$1000
   
   账户080127b91bd484fa0caea965441d01e8f76b5738b48cc16b4ad5ec10eab94135向账户71287a70e839152ae4b4ea77695ae28058c3f268c24438e9b65ef80fe9b24845发起一笔$5000的转账交易。
   080127b91bd484fa0caea965441d01e8f76b5738b48cc16b4ad5ec10eab94135的账户余额不足,可用资金为$1000！
   ```

   

## 示例操作

以下是一些示例操作来演示区块链Demo程序的功能：

### 创建矿工账户

在`main.py`中，您可以创建不同的矿工账户，例如：

```python
miner1 = Miner("Alice")
miner2 = Miner("Bob")
```

### 添加交易

在`main.py`中，您可以添加交易，例如：

```python
transaction = Transaction(miner1.account_address, miner2.account_address, 500)
block_chain.add_transaction(transaction)
```

### 挖矿

在`main.py`中，您可以调用`mine_block`函数来挖矿，例如：

```python
mine_block(block_chain=block_chain, mine=miner1)
```

### 查看余额

在`main.py`中，您可以使用`get_balance_by_address`函数来查看矿工的账户余额，例如：

```python
balance = block_chain.get_balance_by_address(miner1.account_address)
print("矿工账户余额：", balance)
```

## 功能说明

### 区块链

- 创建区块链：在`BlockChain.py`中，通过实例化`BlockChain`类来创建一个新的区块链对象。初始时会生成一个创世区块。

- 添加交易：通过调用`add_transaction`方法，您可以向待处理交易列表中添加新的交易。

- 挖矿：通过调用`mine_block`方法，您可以将待处理的交易打包成一个新的区块，并添加到区块链中。

- 查看余额：通过调用`get_balance_by_address`方法，您可以根据地址查看对应账户的余额。

### 区块

- 区块哈希值：每个区块都有一个唯一的哈希值，由区块的内容和前一个区块的哈希值计算得出。

- 交易列表的默克尔根哈希值：每个区块包含一个交易列表，通过计算交易列表的默克尔根哈希值来保证交易的完整性。

### 矿工

- 挖矿奖励：矿工在成功挖出新区块后，会获得一定数量的挖矿奖励。

## 注意事项

- 该Demo程序是一个简化版的区块链实现，仅用于教学和演示目的。

- 该Demo程序并未考虑真实的网络通信、加密算法和共识机制等复杂功能。

- 在实际的区块链应用中，需考虑安全性、性能和可扩展性等方面的问题。



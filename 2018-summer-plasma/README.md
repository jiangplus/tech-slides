
## Plasma
by jiangplus

---

# Layer2

 * 对于一个 scalable 的分布式系统， scale out 是惟一的出路

 * layer2 网络将应用层和共识层分离开来，提供可伸缩，可并行，可插拔的扩展方式

 * 对于侧链和状态通道，都减少了参与局部共识的节点数量，提高了局部性

---

# Plasma

 * 基于 Map/Reduce 的思想设计的分层多链结构

 * 资产从主链的合约锁定，侧链的矿工将资产转入，在侧链上进行交易

 * 侧链周期性的把 Merkle Proof 提交到上一级主链上，依赖主链见证历史

 * 侧链资产可以在主链上退出，无需侧链矿工的干预

 * 侧链可以有自己的子链，形成树状的层次结构

---

# Plasma 侧链的结构

 * 侧链与主链的关系相对独立，可以是 PoA 或者 PoS，只需要少量节点参与出块

 * 定期将所包含的 UTXO 的 Merkle Tree Root 提交到主链，由 operator 数字签名

 * 侧链上可以进行低成本，高吞吐的交易

 * 侧链保证出块历史的唯一性，否则被扣除抵押金，并且回滚区块

---

# Plasma 的退出

 * 安全的，不依赖侧链矿工的退出机制是 Plasma 的核心

 * 用户将持有的 UTXO 及 Merkle Proof 提交到主链申请退出，等待挑战期

 * 其他用户在这段期间可以提交 UTXO 被花掉的证据

 * 如果用户的退出没有有效的挑战，则可以成功提现

 * 如果矿工提交了事实上无效的交易，用户应当发起退出，并且更早的 UTXO 有更高的优先级

---

# 侧链和状态通道的比较

### Pros

 * 大大减少通道通讯的数量，一对多 vs 一对一

 * 子链状态的更新不需要全量参与者在线进行签名

 * 更容易开发和设计，更容易支持智能合约，模型更加通用

---

#### Cons

 * data availability

 * 隐私性

---

# Thank you

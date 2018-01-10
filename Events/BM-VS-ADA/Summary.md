
### BM怼cardano事件
[已收录至 steemit.com](https://steemit.com/cardamon/@dan/peer-review-of-cardano-s-ouroboros)
- BM认为ada抄袭（copy）了他的工作，但是没有提他，原文：
`（ Ouroboros is a copy of Delegated Proof of Stake (DPoS) with a few counter-productive modifications. In fact their paper refers to the term “πDPoS” 17 times without mentioning or recognizing any of my prior work.）`

- 结果上，BW认为ada的性能和效率完败

类目 | 出块 | 稳定
--- | --- | ---
EOS | 0.5 seconds | <= 2 seconds
Ouroboros | 20 seconds | > 5 hours

- ada的安全在工程上不可行：400公斤的防弹衣没法穿。
- 对DPOS的分析
   - 选人 （Selecting a set of block producers）
   - 排队 （Scheduling the producers into time slots）
- 选人
  - 时间轮： 【BTS:1h】  *vs*  【Ouroboros：5 days】
  - 参与要求：【Steem：没有下限】 *vs* 【Ouroboros： at least 1% stake】
- 排队
  - 随机性：
     - Steem ：从确定一组里面随机抽
     > uses deterministic scheduling with pseudorandom shuffling

     - Ouroboros ：随机性由随机选定的权益人生成
     > sampling from a source of provable randomness created by a committee of randomly selected stakeholders
  - 安全性：
     - Steem / BitShares / EOS 靠投票（人为）
     > select a set of unlikely to collude entities by approval voting then schedule them in a pseudorandom order。 同时EOS要取消shuffle （ EOS will be removing the random shuffle all together.）

     - Ouroboros 随机选择导致时间和延时无法预期
     > Ouroboros the length of time until 2/3+ of the stake is “randomly selected” is not known. unpredictable latency like bitcoin
- 分布式安全（Distribution Security Issues）
   - Steem 14 people confirm a block each round.
   - 只有投票才能对抗基于stake权重的中心化
 stake-weighted voting creates a very high centralization that can only be countered with approval voting 
   - Corruption takes place at the individual level, not the stake level. it is wrong to assume that large stake holders will behave like a group of smaller stakeholders of similar size

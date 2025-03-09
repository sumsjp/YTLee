### 小節整理：文章重點歸納

#### 1. 核心主題
- 探討網絡剪枝（Network Pruning）的效果及其背後的理論機制。
- 比較兩種主要假設：**Lottery Hypothesis** 和 **Weight Agnostic Networks (WAN)**。

#### 2. 主要觀念
##### a. Lottery Hypothesis（ lottery hypothesis）
- 提出大網絡中存在「贏家通喫」的參數，這些參數在剪枝後的小網絡中能夠保持較好的性能。
- 剪枝過程通過借用大網絡中的隨機參數來提升小網絡的性能。

##### b. Weight Agnostic Networks (WAN)
- 表明即使網絡的所有參數都是隨機初始化或固定爲常數（如1.5），也可以在一定程度上實現良好的性能。
- 指出網絡的結構設計可能比參數本身更重要。

#### 3. 主要問題
##### a. Lottery Hypothesis 的局限性
- **Rethinking The Value Of Network Pruning** 這篇文章提出了相反的觀點，指出Lottery Hypothesis的現象可能僅在特定條件下成立。
- 實驗表明，當學習率較高時，無法觀察到Lottery Hypothesis的效果。

##### b. 剪枝後網絡訓練的挑戰
- 直接訓練小網絡（從隨機初始化開始）通常被認爲性能不如先訓練大網絡再進行剪枝的方法。
- 但實驗發現，如果給予足夠多的訓練 epochs，直接訓練的小網絡可以達到與剪枝後網絡相當甚至更好的性能。

#### 4. 解決方法
##### a. 針對 Lottery Hypothesis 的質疑
- **Rethinking The Value Of Network Pruning** 提出通過增加學習率或調整剪枝策略（如結構化剪枝）來驗證Lottery Hypothesis的普適性。
- 強調實驗條件（如學習率、訓練 epochs 等）對結果的重要影響。

##### b. 直接訓練小網絡
- 建議直接訓練小型網絡，並給予足夠的訓練.epoch數，可以避免對大網絡剪枝的依賴。
- 指出剪枝的優勢可能更多地來源於模型搜索（model search）而非簡單的參數保留。

#### 5. 結論與展望
##### a. Lottery Hypothesis 的適用性
- Lottery Hypothesis 可能在特定條件下成立，但其普適性仍需進一步研究。
- 不同的剪枝策略和訓練參數可能影響其效果。

##### b. WAN 的啟發
- 網絡性能不一定完全依賴於精細調控的參數，結構設計的重要性不容忽視。

##### c. 未來研究方向
- 探討不同學習率和訓練策略對Lottery Hypothesis的影響。
- 研究結構化剪枝（如通道剪枝）是否能更好地支撐Lottery Hypothesis。
- 深入分析直接訓練小型網絡的可行性與優勢。

#### 6. 參考文獻
- Lottery Hypothesis: ICLR 2019
- Rethinking The Value Of Network Pruning: ICLR 2019
- Weight Agnostic Networks: Arxiv （早期版本）

---

### 總結
文章主要圍繞網絡剪枝的效果展開討論，探討了Lottery Hypothesis 和 WAN 的核心觀念及其局限性。實驗結果表明，Lottery Hypothesis 的效果可能受限於特定條件（如學習率、訓練epochs等），而直接訓練小型網絡在某些情況下可以取得不俗的性能。未來的研究需要進一步驗證這些假說的普適性並探索更有效的剪枝策略。
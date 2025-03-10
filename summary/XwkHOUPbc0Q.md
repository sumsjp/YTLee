### 文章重點整理

#### 核心主題
- 探討使用分類器進行異常檢測的局限性及其改進方法。

#### 主要觀念
1. 分類器在異常檢測中的應用及其潛在問題。
2. 異常數據收集的困難性。
3. 生成模型（Generative Models）在解決異常數據不足問題中的作用。

#### 問題原因
- **分類器局限性**：分類器基於訓練數據學習正常類別，對於未見過的新類（如草泥馬、老虎等），可能無法準確分類，導致邊界信心分數低。
- **異常數據稀少**：實際應用中，異常數據往往難以收集，影響模型性能。

#### 解決方法
1. **多任務學習**：
   - 訓練分類器同時學習正常數據的高信心和異常數據的低信心。
2. **生成模型輔助**：
   - 使用生成模型（如GANs）生成人工合成的異常數據，補充訓練集。
3. **調整信心計算機制**：
   - 通過熵等方法強化異常檢測中的信心分數區分。

#### 優化方式
1. **混合訓練策略**：
   - 結合真實異常數據和生成數據進行聯合訓練，提升模型魯棒性。
2. **領域適應**：
   - 針對特定應用場景優化生成模型，確保生成數據與實際數據分布一致。

#### 結論
- 雖然直接使用分類器進行異常檢測存在局限，但通過結合多任務學習和生成模型等方法，可以有效提升其性能。
- 未來研究應關注如何更高效地利用合成數據和改進分類器的邊界信心評估機制。
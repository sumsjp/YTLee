### 文章整理：Transformer 模型中的	layer normalization	及其優化研究

#### 1. 核心主題
- **主題**：探討 Transformer 模型中(encoder) 中的 layer normalization (LN) 的設計、問題及優化方法。

#### 2. 主要觀念
- **原始 Transformer 架構中的 LN 設計**：
  - 在每個 encoder block 內，先進行 self-attention 和 feed-forward 網絡，然後在輸出端進行 residual 連接和 layer normalization。
  
- **LN 的作用**：
  - Layer normalization 用於穩定網絡的訓練過程，通過標準化特徵值，減少內部協變量偏移。

#### 3. 問題原因
- **原始設計的問題**：
  - 原始 Transformer 架構中將 layer normalization 放在 residual 連接之後，可能導致梯度消失或不穩定。
  
- **Batch Normalization 的局限性**：
  - Batch normalization 在 Transformer 中表現不佳，因爲其依賴於小批量數據，而Transformer通常處理長序列，難以有效利用批次信息。

#### 4. 解決方法
- **優化 LN 的位置**：
  - 將 layer normalization 移至 residual 連接之後，即在每個 sub-layer 輸入端進行標準化，而非輸出端。
  
- **引入 Power Normalization**：
  - 提出一種新的歸一化方法——Power Normalization，旨在替代傳統的 batch 或層歸一化，通過調整冪次參數來提高模型性能。

#### 5. 優化方式
- **重新設計 encoder block**：
  - 在每個 sub-layer 的輸入端進行 layer normalization 和 residual 連接，以提升訓練的穩定性。
  
- **Power Normalization 的實現**：
  - 引入可學習的冪次參數，通過自適應調整歸一化方式，增強模型對不同特徵分布的適應能力。

#### 6. 結論
- **改進後的效果**：
  - 將 layer normalization 移動到 residual 連接之後可以顯著提高訓練速度和模型性能。
  
- **Power Normalization 的優勢**：
  - 在某些任務中，Power Normalization 可以提供比傳統層歸一化更好的性能，尤其是在特徵分布變化較大的情況下。

#### 7. 展望
- **未來研究方向**：
  - 探索更多適應 Transformer 架構的歸一化方法，結合可學習參數和自適應機制，進一步提升模型的泛化能力和訓練效率。
### 核心主題
- **Self-Attention Mechanism**: 自注意力機制是 transformer 模型的核心組件，用於捕獲序列中元素之間的相互依賴性。

### 主要觀念
- **Self-Attention 的計算方式**：
  - **_Query**, **Key**, 和 **Value** 向量通過線性變換生成。
  - 計算各 Query 與 Key 的相似度（注意力分數）。
  - 根據相似度加權 Value，得到最終的CONTEXT_VECTOR。

- **Self-Attention 的應用**：
  - 傾向於捕獲長距離依賴，但計算複雜度高（O(n²)），影響實時性和效率。

### 問題原因
- **計算複雜度高**：原始 Self-Attention 機制的時間複雜度為 O(n²)，在處理大型數據時效率低下。
- **缺乏結構信息**： traditional Self-Attention 預先無關聯信息，需由模型自行學習元素之間的關係。

### 解決方法
- **引入圖結構信息**：
  - 在圖神經網絡中，利用邊信息限制注意力分數的計算，只考慮.isConnected 的節點。
  - 例如，在圖結構中，若兩個節點無邊連接，則其注意力分數設為0。

### 優化方式
- **輕量級 Self-Attention 變體**：
  - 各種改進版本如 Linformer、Performer 和 Reformer 等，通過降低計算複雜度提高速度。
  - 這些方法通常 trade-off 性能和速度。

- **Efficient Transformers 調研**：
  - 文獻回顧報告《Efficient Transformers: A Survey》探討了多種優化技術，包括稀疏化、低秩近似等。

### 結論
- **Self-Attention 的重要性**：作為 transformer 模型的關鍵組件，其性能和效率直接影響模型效果。
- **未來研究方向**：如何在保持或提升性能的前提下降低計算複雜度，是 Self-Attention 風格的重要研究課題。

### 參考文獻
- Vaswani, et al. "Attention Is All You Need."
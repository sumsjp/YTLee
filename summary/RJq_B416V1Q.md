# The Role and Importance of Self-Attention in Continuous Input Reconstruction: An Empirical Study

## 小節整理

### 1. 核心主題  
- 探討自注意力機制（Self-Attention）在連續輸入重建任務中的作用和重要性。  
- 分析不同類型的注意力頭（Attention Heads）對下遊任務的影響。  

### 2. 主要觀念  
- 自注意力機制能夠捕捉序列中的全局信息，並在重建任務中表現出強大的能力。  
- 注意力頭可以分爲三類：** diagonal, vertical, 和 global**，每種類型在處理不同類型的信息時具有不同的作用。  

### 3. 問題原因  
- 不同類型的注意力頭對下遊任務的重要性存在差異。  
- 部分注意力頭可能對模型性能貢獻較小甚至產生負面影響。  

### 4. 解決方法  
- 提出一種基於注意力頭重要性的評估指標：** globalness, verticality, 和 diagonality**，用於量化不同類型注意力頭的貢獻。  
- 通過逐步剪枝（Pruning）實驗，驗證不同類型注意力頭對下遊任務的影響程度。  

### 5. 優化方式  
- **Diagonal Attention Heads**: 對音素分類任務至關重要，其剪枝會導致性能顯著下降。  
- **Vertical Attention Heads**: 主要影響說話人識別任務，但可能對音素分類任務產生負面影響。  
- **Global Attention Heads**: 對整體表示質量貢獻較小，可適當剪枝以優化性能。  

### 6. 結論  
- 自注意力機制在連續輸入重建任務中表現出強大的能力。  
- **Diagonal Attention Heads** 是核心，對音素分類和說話人識別均至關重要。  
- 可通過剪枝去除超過50%的冗餘注意力頭（尤其是Global類型），在不影響說話人身份的前提下提升音素分類性能。  
- 未來研究可進一步探索注意力頭的多樣性與模型壓縮的可能性。
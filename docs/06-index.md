<details>
<summary>301. [2021-03-12] 【機器學習2021】類神經網路訓練不起來怎麼辦 (四)：損失函數 (Loss) 也可能有影響</summary><br>

<a href="https://www.youtube.com/watch?v=O2VkP8dJ5FE" target="_blank">
    <img src="https://img.youtube.com/vi/O2VkP8dJ5FE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】類神經網路訓練不起來怎麼辦 (四)：損失函數 (Loss) 也可能有影響

# 文章整理：分類任務中的損失函數選擇與優化

## 小節一：核心主題
- 探討在分類任務中選擇合適的損失函數（如均方誤差和交叉熵）對優化過程的影響。
- 強調損失函數的選擇對模型訓練的難易程度及收斂速度的重要性。

## 小節二：主要觀念
1. **損失函數的作用**：
   - 損失函數用於衡量模型預測值與實際值之間的差距。
   - 不同的損失函數會導致不同的錯誤面（error surface）和優化過程。

2. **均方誤差（Mean Square Error, MSE）**：
   - 基本形式：$\text{MSE} = \frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2$。
   - 在分類任務中，尤其是在ソフトマックス後的預測值上使用時，可能會導致優化困難。

3. **交叉熵（Cross-Entropy）**：
   - 基本形式：$\text{CE} = -\frac{1}{n}\sum_{i=1}^{n}[y_i \log(\hat{y}_i) + (1 - y_i) \log(1 - \hat{y}_i)]$。
   - 在分類任務中，尤其是多分類問題中，交叉熵損失函數通常與Softmax激活函數配對使用，具有良好的優化性能。

## 小節三：主要問題與原因
- **均方誤差的局限性**：
  - 在某些初始條件下（如預測值遠離真實值），MSE的梯度非常小，導致模型訓練陷入困境。
  - MSE的錯誤面在高損失區域通常比較平坦，使得梯度下降算法難以有效找到最優解。

- **交叉熵的優勢**：
  - 交叉熵損失函數在高損失區域具有更陡峭的梯度，使得模型能夠更快地調整參數並 convergence。
  - 雖然MSE和交叉熵在分類任務中均可使用，但交叉熵通常更適合分類任務，尤其是當使用Softmax激活時。

## 小節四：解決方法與優化方式
1. **選擇合適的損失函數**：
   - 在分類任務中，推薦使用交叉熵損失函數，尤其是在多分類問題中。
   - 若使用均方誤差，需注意初始化參數，避免模型陷入梯度平坦的區域。

2. **優化算法的選擇**：
   - 使用現代優化算法（如Adam、SGD等）可以幫助模型更有效地 navigates 錯誤面。
   - 調整學習率和動量參數可能有助於改善訓練效果。

3. **參數初始化**：
   - 合適的參數初始化策略（如Xavier_initializer或He_initializer）可以幫助模型避免陷入高損失區域。

## 小節五：結論
- 損失函數的選擇直接影響分類模型的訓練效果和效率。
- 交叉熵損失函數因其在高損失條件下的良好梯度特性，適合用於多分類問題。
- 總體而言，在分類任務中使用交叉熵損失函數可以提高模型訓練的成功率和 convergence 效率。
</details>

<details>
<summary>302. [2021-03-12] 【機器學習2021】類神經網路訓練不起來怎麼辦 (三)：自動調整學習速率 (Learning Rate)</summary><br>

<a href="https://www.youtube.com/watch?v=HYUXEeh3kwY" target="_blank">
    <img src="https://img.youtube.com/vi/HYUXEeh3kwY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】類神經網路訓練不起來怎麼辦 (三)：自動調整學習速率 (Learning Rate)

# 文章重點整理

## 核心主題
文章主要探討深度學習中常見的優化問題及其解決方法，特別是針對崎嶇的錯誤表面（error surface）進行優化。

## 主要觀念
1. **錯誤表面的特性**：在深度學習中，錯誤表面往往非常崎嶇，存在多個局部最小值和鞍點。
2. **傳統優化算法的限制**：如原始梯度下降法，在面對崎嶇錯誤.surface時效果不佳，容易陷入局部最小值或振盪。

## 問題原因
1. **缺乏動量（Momentum）**：原始梯度下降缺乏對過去梯度信息的利用，無法有效加速 convergence。
2. **學習率不適宜**：固定 learning rate 在不同地帶可能效果不佳，需要動態調整。
3. **錯誤表面的複雜性**：崎嶇的錯誤.surface 導致傳統算法難以有效找到全局最小值。

## 解決方法
1. **引入動量（Momentum）**：
   - 考慮過去所有梯度的方向和大小，加速 convergence。
2. **自適應學習率調整**：
   - 使用 RMSProp 等算法，根據梯度的二階統計量（如均方差）動態調整 learning rate。
3. **動態學習率調度（Learning Rate Scheduling）**：
   - 隨訓練進展自動調整 learning rate，初期用小 learning rate 探索，後期增大以加速 convergence。

## 優化方式
1. **Adam 管理器**：整合了 Momentum 和 RMSProp 的優點，計算梯度的動量和均方差，並根據這些信息自適應地調整參數更新。
2. **RAdam（Robust Adam）**：
   - 在 Adam 的基礎上進一步改進，提供更穩定的訓練過程，特別是在小批量數據情況下。

## 結論
1. **Adam 管理器的優越性**：Adam 是目前最常用的優化算法之一，因其結合了多種優化技術，在各種任務中表現傑出。
2. **未來研究方向**：
   - 探索更多優化的理論方法。
   - 改進網絡架構或激勵函數以降低錯誤.surface 的崎嶇度。

---

# 全文概要
文章全面探討了深度學習中的優化問題，特別是面對崎嶇錯誤表面時的挑戰與解決方案。介紹了從原始梯度下降到更先進的.Adam 管理器的演進過程，強調了動量、自適應學習率和學習率調度的重要性。最後提出了一些未來的研究方向，旨在進一步提升優化算法的效果和效率。
</details>

<details>
<summary>303. [2021-03-12] 【機器學習2021】自注意力機制 (Self-attention) (上)</summary><br>

<a href="https://www.youtube.com/watch?v=hYdO9CscNes" target="_blank">
    <img src="https://img.youtube.com/vi/hYdO9CscNes/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自注意力機制 (Self-attention) (上)

### 小節歸納

#### 核心主題
- **多頭注意力機制（Multi-Head Attention）**：本文圍繞如何從序列中抽取重要資訊展開討論，核心在於通過注意力分數（Attention Scores）來加權聚合序列中的向量。

#### 主要觀念
1. **注意力分數的計算**：
   - 通過Query（q）、Key（k）和Value（v）的線性變換來計算每個位置對其他位置的注意力分數。
   - 注意力分數反映了一個位置對另一個位置的重要性。

2. **Soft-Max函數的作用**：
   - 將原始的注意力分數規範化到概率分布，確保所有分數之和為1。
   - 常見於分類任務中，但也可根據具體場景選擇其他激活函數。

3. **加權聚合**：
   - 根據注意分數對Value向量進行加權求和，最終得到聚合結果。

#### 問題原因
- 在處理序列數據時，直接使用全連接層會忽略序列的結構信息。
- 需要一種有效的方法來捕獲序列中不同位置之間的相互作用。

#### 解決方法
1. **查詢（Query）、鍵（Key）和值（Value）**：
   - 對每個位置的向量進行線性變換，得到(Query、Key、Value)三元組。
   
2. **計算注意力分數**：
   - 通過內積或點乘來衡量不同位置之間的相關性。

3. **Soft-Max規範化**：
   - 將原始分數轉換為概率分布，確保加和為1。

4. **加權聚合**：
   - 根據注意力分數對Value向量進行加權求和，得到最終的聚合結果。

#### 優化方式
- 可以嘗試不同的激活函數（如ReLU）來替代Soft-Max，根據實驗效果選擇最適合的方案。
- 通過多頭注意力機制進一步提升模型性能，允許模型在不同子空間中學習多種類型的注意力。

#### 結論
- 注意力機制能夠有效地捕獲序列中重要信息，增強模型對長距離依存關係的捕捉能力。
- 該方法已在多個自然語言處理任務中取得成功，具有廣泛的應用前景。
</details>

<details>
<summary>304. [2021-03-12] 【機器學習2021】卷積神經網路 (Convolutional Neural Networks, CNN)</summary><br>

<a href="https://www.youtube.com/watch?v=OP5HcXJg2Aw" target="_blank">
    <img src="https://img.youtube.com/vi/OP5HcXJg2Aw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】卷積神經網路 (Convolutional Neural Networks, CNN)

# 文章整理：CNN在特定任務中的適用性分析

## 1. 核心主題
探討卷積神經網絡（CNN）在不同任務中的適用性，特別是下棋和影像處理中的差異。

## 2. 主要觀念
- **CNN的設計依賴於任務特性**：CNN的架構需要根據具體任務的特點進行設計，不能盲目套用。
- **Poolings的局限性**：雖然池化層常用於影像處理以降低維度和提取特徵，但在下棋等任務中並不適用，可能導致信息丟失。

## 3. 問題原因
- **信息丟失的風險**：池化操作可能破壞關鍵的空間信息，影響任務性能。
- **對尺度和旋轉的敏感性**：CNN在固定尺寸和方向上的訓練導致其難以處理不同尺度和旋轉的對象。

## 4. 解決方法
- **任務適配設計**：
  - 針對下棋任務，採用多層卷積而無池化。
  - 針對語言處理，設計適合序列數據的CNN變體（如TextCNN）。
- **數據增強技術**：通過旋轉、縮放等方式擴展訓練數據，提高模型魯棒性。

## 5. 優化方式
- **架構調整**：
  - 使用不同核大小的卷積層以適應多種特徵尺度。
  - 增加Batch Normalization以提升泛化能力。
- **替代方法探索**：引入Transformer等架構解決CNN在序列數據上的局限性。

## 6. 結論
- CNN的應用需根據任務特點量身定製，而非通用方案。
- 數據增強和架構優化是提升模型魯棒性的關鍵手段。
</details>

<details>
<summary>305. [2021-03-12] [ML 2021 (English version)] Lecture 3: Roadmap of Improving Model</summary><br>

<a href="https://www.youtube.com/watch?v=3qgKpBptyFY" target="_blank">
    <img src="https://img.youtube.com/vi/3qgKpBptyFY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 3: Roadmap of Improving Model

### 文章重點整理

#### 核心主題
- **機器學習模型的錯誤分析與改進**
- **數據分 distribution 集問題（Mismatch）的影響與應對**

#### 主要觀念
1. **過度擬合 (Overfitting) 的定義與解決方法**  
   - 過度擬合是指模型在訓練數據上表現良好，但在未見過的測試數據上效果不佳。
   - 解決方法包括增加更多數據、使用正則化技術（如Dropout）等。

2. **分 distribution 集問題 (Mismatch)**  
   - 分集指的是訓練數據和測試數據之間存在不同的分布，導致模型性能下降。
   - 分集問題無法通過增加訓練數據來解決，因為數據的分布差異是根本原因。

#### 問題原因
1. **過度擬合的原因**  
   - 訓練數據不足或複雜度過高的模型易導致過度擬合。

2. **分 distribution 集問題的原因**  
   - 訓練數據和測試數據來源不同，例如時間差異（如2020年數據訓練，2021年數據測試）。
   - 數據分布的自然變化或人工幹擾導致分集。

#### 解決方法
1. **過度擬合的解決方法**  
   - 增加訓練數據量。
   - 使用正則化技術（如Lasso、Ridge_regression等）。
   - 簡化模型複雜度。

2. **分 distribution 集問題的解決方法**  
   -仔細設計數據分割方式，確保訓練和測試數據的分布相似。
   -若不可避免分集，可使用遷移學習或強化模型的泛化能力。

#### 優化方式
1. **數據收集與 preprocessing**  
   - 確保數據來源和分布的多樣性。
   - 清洗數據以消除噪聲。

2. **模型結構設計**  
   - 選擇適合數據特性的模型架構。
   - 使用ensemble技術（如Bagging、Boosting）提高模型魯棒性。

#### 結論
- **模型性能受多重因素影響**  
   - 過度擬合和分集問題是常見的兩大挑戰。
- **數據與模型的重要性**  
   - 高質量的數據和恰當的模型設計是確保機器學習系統性能的關鍵。
- **未來研究方向**  
   - 探索更有效的分 distribution 調整方法。
   - 研究抗分集的深度學習技術。

---

### 文章結論
文章主要探討了機器學習模型在實際應用中常遇到的錯誤類型，特別是過度擬合和分 distribution 集問題。作者通過具體案例分析，強調了解決這些問題的重要性，並提出了一系列實用的解決方案和優化策略。最終結論指出，數據質量與模型設計是影響機器學習性能的核心因素，未來的研究應進一步探索如何有效應對分 distribution 問題。
</details>

<details>
<summary>306. [2021-03-12] [ML 2021 (English version)] Lecture 4: What to do when optimization fails? (1/4)</summary><br>

<a href="https://www.youtube.com/watch?v=yz7QS1I6omw" target="_blank">
    <img src="https://img.youtube.com/vi/yz7QS1I6omw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 4: What to do when optimization fails? (1/4)

### 文章整理：深度學習模型訓練中的收斂問題與 saddle point 的影響

#### 核心主題  
本文探討了深度學習模型在訓練過程中常遇到的梯度消失或不易更新的問題，特別是 saddle point（鞍點）現象對模型收斂的影響。

#### 主要觀念  
1. **Error Surface 的高維特性**：模型參數通常超過一百萬甚至上億，導致誤差 surface 存在於十-million 維度的高維空間。
2. **Local Minima vs Saddle Point**：
   - Local minimum 是所有方向損失都增加的點。
   - Saddle point 是某些方向損失增加，而其他方向損失降低的點。
3. **梯度消失與參數更新停止**：在 saddle point 處，梯度可能非常小，導致訓練過程停滯。

#### 問題原因  
1. **高維空間中 saddle point 的普遍存在**：
   - 研究表明，在深度學習模型中，ritical points（如 local minima 和 saddle point）通常具有混合的特徵值分佈。
   - 在 experiments 中，minimum ratio（正特徵值數量 / 所有特徵值數量）大約在 0.5 到 0.6 之間，表明一半以上方向會增加損失。
2. **梯度下降算法敏感性**：傳統的梯度下降方法在高維空間中容易陷入 saddle point。

#### 製定方式與研究數據  
1. **實驗結果**：
   - 每個 points 表示訓練完成後網路的 Hessian 矩陣。
   - Vertical axis：training 中最小損失值。
   - Horizontal axis：minimum ratio（正特徵值比例）。
2. **數據分析**：
   - 大部分 critical points 的 minimum ratio 在 0.5 到 0.6，表明 saddle point 現象普遍存在。
   - 即使是在 extreme cases 中，negative eigenvalues 仍然佔總數的 50% 左右。

#### 課題與挑戰  
1. **Local Minima 的罕見性**：在實際訓練中，almost 不可能找到所有特徵值都是正的情況。
2. **Saddle Point 的影響**：高維度下 saddle point 現象更容易發生，導致梯度下降過程中的更新困難。

#### 結論  
1. 在深度學習模型中，local minima 並不常見，更多的是 saddle points 造成訓練停滯。
2. 高維空間的特性使得 saddle point 現象更加普遍，這對傳統 gradient descent 方法提出了挑戰。

---

本文強調了高維度下 saddle point 的影響，並通過 experiments 表明，在深度學習中 local minima 並不常見，主要問題出在 saddle points。研究結果為改進訓練算法提供了重要啟發。
</details>

<details>
<summary>307. [2021-03-12] [ML 2021 (English version)] Lecture 5: What to do when optimization fails? (2/4)</summary><br>

<a href="https://www.youtube.com/watch?v=MNoEQ9w-AbE" target="_blank">
    <img src="https://img.youtube.com/vi/MNoEQ9w-AbE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 5: What to do when optimization fails? (2/4)

### 小節整理：動量在梯度下降中的應用與作用

#### 1. 核心主題
- 探討在優化算法中引入動量（Momentum）的作用及其對梯度下降性能的提升。

#### 2. 主要觀念
- 動量是一種優化技術，用於加速梯度下降過程並幫助模型更快地收斂。
- 動量通過整合歷史梯度信息來調整當前更新步長，從而減少隨機方向的影響。

#### 3. 問題原因
- 梯度下降算法在面對高度非凸的優化問題時，容易陷入局部極小值或 saddle point。
- 在某些情況下，特別是當目標函數具有噪聲較大的梯度時，傳統的梯度下降方法可能會搖擺不定，導致收斂速度變慢。

#### 4. 解決方法
- 引入動量的概念，通過累加歷史梯度信息來調整當前更新方向。
- 具體實現上，動量項通常是一個參數（λ）與前一步的動量向量的乘積，再加上當前梯度的影響。

#### 5. 優化方式
- 動量優化算法的核心公式爲：
  \[
  m_t = λm_{t-1} - ηg_t
  \]
  其中，\(m_t\) 是當前動量向量，\(λ\) 是動量係數（0 < λ ≤ 1），\(η\) 是學習率，\(g_t\) 是當前梯度。
- 動量優化算法通過累加動量向量來加速收斂，並減少隨機方向的影響。

#### 6. 理論分析
- 動量項的引入使得優化過程不僅依賴於當前梯度，還考慮了歷史梯度信息。
- 當模型接近極小值時，動量可以幫助模型「滾過」可能存在的局部極小值或 saddle point，從而找到更優解。

#### 7. 結論
- 動量是一種有效的優化技術，在實際應用中能夠顯著提升梯度下降算法的性能和收斂速度。
- 在深度學習等複雜優化問題中，動量優化方法（如Adam、SGD with Momentum）已經成爲常用的優化算法之一。
</details>

<details>
<summary>308. [2021-03-18] [ML 2021 (English version)] Lecture 8: Classification (Short Version)</summary><br>

<a href="https://www.youtube.com/watch?v=jqVONJ-Wn8w" target="_blank">
    <img src="https://img.youtube.com/vi/jqVONJ-Wn8w/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 8: Classification (Short Version)

### 核心主題  
本篇文章主要探討在多類分類任務中，選擇不同的損失函數（均方錯誤 vs. 電熵損失）對模型訓練困難度的影響，特別是在誤差表面平滑性方面的差異。  

---

### 主要觀念  
1. **Softmax函數的作用**：將網絡的原始輸出轉換為概率分佈，使其適合分類任務。  
2. **損失函數的作用**：衡量模型預測結果與真實標籤之間的差距，引導模型參數調整以最小化損失。  

---

### 問題原因  
1. **均方錯誤的缺點**：  
   - 在誤差表面中，某些區域（如分類任務中預測概率偏差較大時）的梯度非常小，導致 gradient descent 方法在這些區域近く訓練時難以有效移動參數。  
   - 這使得模型陷入局部最小值或訓練速度極為緩慢。  

2. **電熵損失的優勢**：  
   - 電熵損失能夠提供更陡峭的梯度，即使在預測概率偏差較大時，也能有效引導參數更新，從而更容易找到全局最優解。  

---

### 解決方法與優化方式  
1. **選擇合適的損失函數**：  
   - 在分類任務中，推薦使用電熵損失函數（cross-entropy loss），因其能更好地引導模型訓練至合理區域。  

2. **使用先進的 optimizer**：  
   - 如Adam optimizer，在均方錯誤作為損失函數的情況下，可以自動調整學習率，幫助模型克服梯度較小的區域。  

3. **誤差表面的平滑性與可訓練性**：  
   - 電熵損失函數能有效改善誤差表面的可訓練性，降低訓練困難度。  

---

### 理論支持與實驗證據  
1. **理論分析**：  
   - 電熵損失函數在分類任務中具有良好的分離性能，通過最大化預測概率與真實標籤之間的交叉熵，能夠更有效地將模型輸出拉向正確的分佈。  

2. **實驗示例**：  
   - 本文通過三類分類的具體案例，展示了均方錯誤在某些區域梯度接近零，導致訓練困難；而電熵損失則能在這些區域保持較大的梯度，加速參數更新。  

---

### 結論  
1. 電熵損失函數在多類分類任務中比均方錯誤更適合用於模型訓練，因其能提供更穩定和有效的梯度信號。  
2. 總體而言，選擇合適的損失函數是提升模型訓練效果和效率的重要因素之一。  

---

### 具體研究方向  
**研究方向：深度學習中損失函數對分類任務訓練影響的理論分析與應用研究**  
- 探索不同損失函數在多類分類任務中的性能差異，並分析其背後的理論原因。  
- 研究如何通過設計新型損失函數或結合優化算法，進一步提升模型訓練效率和效果。
</details>

<details>
<summary>309. [2021-03-18] [ML 2021 (English version)] Lecture 9: Convolutional Neural Networks</summary><br>

<a href="https://www.youtube.com/watch?v=I4eLIsPM9Yc" target="_blank">
    <img src="https://img.youtube.com/vi/I4eLIsPM9Yc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 9: Convolutional Neural Networks

# 文章重點整理

## 核心主題
本文探討卷積神經網絡（CNN）在不同任務中的適用性及其局限性，特別是其在圖像處理、語音識別和語言處理中的應用差異。此外，文章還討論了CNN在處理圖像縮放和旋轉方面的不足，並提出了解決方案。

## 主要觀念
1. **CNN的應用領域**：
   - 圖像處理：CNN在圖像分類任務中表現出色。
   - 語音識別：CNN被用於語音識別，但需根據語言特性設計接收野。
   - 語言處理：CNN在某些自然語言處理任務中也有應用。

2. **CNN的局限性**：
   - **無法處理圖像縮放和旋轉**：CNN對圖像大小的變化敏感，可能導致識別失敗。
   - **缺乏通用性**：CNN的設計需根據具體任務調整接收野和參數共享策略。

3. **Go神經網絡設計案例**：
   - 在AlphaGo中，未使用池化操作，而是通過增加層和調整濾波器數量來提升性能。這表明網絡架構的設計需根據任務需求靈活調整。

## 問題原因
1. **CNN的局限性源於其架構設計**：
   - 接收野固定：CNN的接收野通常基於圖像的空間特徵設計，難以適應不同尺度的對象。
   - 參數共享策略：參數共享策略在語音和語言處理中可能不適用，需根據任務特性進行調整。

2. **池化操作的局限性**：
   - 池化操作雖能降低計算複雜度和過擬合風險，但在某些任務（如遊戲AI）中反而不利於性能提升。因此，是否使用池化需根據具體任務決定。

## 解決方法
1. **數據增強技術**：
   - 通過縮放、切割和旋轉圖像生成更多樣化的訓練數據，幫助CNN適應不同尺度和角度的對象。
   
2. **靈活的網絡架構設計**：
   - 根據具體任務需求調整接收野大小和參數共享策略。例如，在AlphaGo中未使用池化操作而增加了層的數量。

## 優化方式
1. **根據任務特性設計網絡架構**：
   - 在圖像處理任務中，需考慮對象的尺度變化。
   - 在語音識別和語言處理中，接收野的設計應基於語言特徵。
   
2. **探索替代架構**：
   - 對於CNN的局限性（如無法處理縮放和旋轉），可嘗試使用其他架構（如特殊變換層）進行優化。

## 結論
1. **CNN的應用需謹慎選擇任務**：
   - CNN在圖像分類任務中表現優異，但在語音識別和語言處理中需根據具體需求調整設計。
   
2. **網絡架構設計的重要性**：
   - 網絡架構的設計應基於對任務的深入理解。例如，在AlphaGo中未使用池化操作而通過增加層數量來提升性能。

3. **未來研究方向**：
   - 探索更通用的網絡架構，以適應不同尺度和角度的對象。
   - 開發新的技術手段（如特殊變換層）以克服CNN的局限性。
</details>

<details>
<summary>310. [2021-03-18] [ML 2021 (English version)] Lecture 10: Self-attention (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=0djMUi2-uV4" target="_blank">
    <img src="https://img.youtube.com/vi/0djMUi2-uV4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 10: Self-attention (1/2)

### 核心主題
- **注意力機制（Attention Mechanism）**：文章探討了如何通過注意力機制來提取序列中最相關的信息。

### 主要觀念
1. **注意力分core思想**：
   - 通過計算序列中每對元素的注意力分core（attention score），確定哪些元素相互之間具有強烈關聯。
2. **Softmax函數的作用**：
   - 將原始的注意力分core值轉換為概率分佈，確保所有分core值之和為1，從而實現加權求和的操作。

### 問題與原因
- **信息過載問題**：在處理長序列數據時，直接提取所有信息可能導致模型性能下降，且計算量過大。
- **重要性識別不足**：傳統方法缺乏有效手段來識別並強調序列中最重要的部分。

### 解決方案
1. **注意力分core的引入**：
   - 計算每對元素的注意力分core，量化它們之間的相互作用。
2. **Softmax函數的應用**：
   - 將原始分core值轉換為概率分佈，實現加權求和，從而提取序列中最相關的信息。

### 優化方式
1. **激活函數的選擇**：
   - 軟件的最大（Softmax）是最常用的激活函數，但也可以嘗試其他函數（如ReLU）以獲得更好的性能。
2. **自注意力的計算**：
   - 除了計算序列中元素之間的相互作用，還可以考慮元素自身的注意力分core，進一步提升模型的表達能力。

### 結論
- 注意力機制為序列數據處理提供了一種有效的信息提取方法。通過計算注意力分core並應用Softmax函數，模型能夠聚焦於最相關的信息，從而提高性能和效率。

---

### Title (英文標題)
"Attention Mechanism: A Comprehensive Overview"

### Abstract (英文摘要)
This article provides a detailed exploration of the attention mechanism, focusing on its core principles and practical applications. By calculating attention scores between elements in a sequence and applying softmax function to normalize these scores, the mechanism effectively extracts relevant information from complex data. The discussion includes key concepts such as self-attention, the role of activation functions, and optimization strategies for improving model performance.
</details>

<details>
<summary>311. [2021-03-26] 【機器學習2021】類神經網路訓練不起來怎麼辦 (五)： 批次標準化 (Batch Normalization) 簡介</summary><br>

<a href="https://www.youtube.com/watch?v=BABPWOkSbLE" target="_blank">
    <img src="https://img.youtube.com/vi/BABPWOkSbLE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】類神經網路訓練不起來怎麼辦 (五)： 批次標準化 (Batch Normalization) 簡介

# 文章整理：Batch Normalization 的核心與爭議

## 核心主題  
- **Batch Normalization（BN）**：一種常見於深度學習中的正規化技術，旨在加速訓練並提升模型性能。  

## 主要觀念  
1. **工作原理**：
   - 在每一批數據上進行均值和方差的正規化。
   - 通過調整參數，使輸出的分布更加穩定。

2. **理論支持**：
   - 改善錯誤表面（error surface），使其更不崎嶇，利於優化算法 convergence。  

3. **實驗證據**：
   - 多項研究顯示 BN 可顯著提升訓練速度與模型性能。  

## 問題原因  
- **Internal Covariate Shift**：早期假說認為，訓練過程中前一層輸出的分佈變化會干擾後一層的訓練，導致 gradient 計算方向不一致。  

## 解決方法  
- **Batch Normalization**：
  - 在每個 mini-batch 上計算均值和方差，並對輸出進行正規化。
  - 引入學習率的調整（如 γ 和 β 的學習），使模型適應不同的分佈變化。  

## 優化方式  
- **Parameter Adjustment**：通過可學習的參數（γ 和 β）使 BN 適應不同數據分佈，提升模型 flexibility。
- **Error Surface 改善**：BN 使錯誤表面更平滑，降低梯度震盪，加速 convergence。  

## 紛爭與辯論  
1. **Internal Covariate Shift 的有效性**：
   - 近期研究質疑 Internal Covariate Shift 是否為訓練的主要問題。
   - 實驗表明，即使分佈變化較大，gradient 方向影響不大。

2. **Batch Normalization 的意外效果**：
   - 有研究指出 BN 的優異性能可能源於其對錯誤表面的偶然改進，而非最初假說。  

## 結論  
- **有效性**：BN 在多數情況下顯著提升訓練效果，但其具體機制仍需進一步研究。
- **未來方向**：探索其他方法來改善錯誤表面，並深入理解 BN 的作用機理。
</details>

<details>
<summary>312. [2021-03-26] 【機器學習2021】Transformer (上)</summary><br>

<a href="https://www.youtube.com/watch?v=n9TlOhRjYoc" target="_blank">
    <img src="https://img.youtube.com/vi/n9TlOhRjYoc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】Transformer (上)

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
</details>

<details>
<summary>313. [2021-03-26] 【機器學習2021】自注意力機制 (Self-attention) (下)</summary><br>

<a href="https://www.youtube.com/watch?v=gmsMY5kc-zw" target="_blank">
    <img src="https://img.youtube.com/vi/gmsMY5kc-zw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自注意力機制 (Self-attention) (下)

# 文章整理：自注意力機制（Self-Attention）的深入探討與應用

## 核心主題
- 自注意力機制（Self-Attention）是Transformer模型的核心組件，廣泛應用於自然語言處理、計算機視覺等領域。
- 探討了自注意力機制在圖神經網絡（GNN）中的應用及其優化方法。

## 主要觀念
1. **自注意力機制的原理**：
   - 通過計算序列中每個元素與其他元素之間的相似性或相關性，生成一個注意力權重矩陣。
   - 根據這些權重對輸入進行加權求和，提取上下文信息。
   
2. **圖神經網絡中的自注意力機制應用**：
   - 利用圖的結構信息（如節點和邊）來限制注意力計算，減少不必要的計算量。
   - 通過僅考慮相連節點之間的注意力分數，提升模型效率。

3. **自注意力機制的變體與優化**：
   - 出現了多種針對不同場景的自注意力變體，如Linformer、Performer等，旨在降低計算複雜度並提高速度。
   - 這些變體通常在性能和速度之間尋求平衡，以適應不同的應用場景。

## 問題原因
1. **計算複雜度過高**：
   - 原始的自注意力機制時間複雜度爲O(n²)，對於大規模數據來說計算量巨大。
   
2. **圖結構信息未充分利用**：
   - 在傳統的自注意力機制中，節點之間的關係是通過模型自動學習得到的，未能充分結合先驗知識（如圖中的邊信息）。

## 解決方法
1. **優化自注意力機制**：
   - 引入低秩分解、稀疏化等技術減少計算量。
   
2. **結合圖結構信息**：
   - 在計算注意力權重時，僅考慮相連節點對的注意力分數，忽略其他無關節點之間的關係。
   - 利用邊信息指導注意力計算，提高模型效率。

## 優化方式
1. **降低計算複雜度**：
   - 使用更高效的矩陣運算（如低秩分解）或稀疏化技術，減少計算量。
   
2. **結合先驗知識提升效率**：
   - 在圖結構中，利用已知的邊信息限制注意力計算範圍，避免不必要的計算。

## 結論
- 自注意力機制在多個領域展現出強大的潛力，但其計算複雜度和對大規模數據的處理能力仍需進一步優化。
- 通過結合先驗知識（如圖結構信息）和引入新的技術手段，可以有效提升自注意力機制的效率和性能。
</details>

<details>
<summary>314. [2021-04-09] 【機器學習2021】Transformer (下)</summary><br>

<a href="https://www.youtube.com/watch?v=N6aRv06iv2g" target="_blank">
    <img src="https://img.youtube.com/vi/N6aRv06iv2g/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】Transformer (下)

# 文章重點整理

## 核心主題
本文主要探討TRANSFORMER模型在自然語言處理任務中的應用及其訓練技巧。文章圍繞ENCODER和DECODER結構、訓練過程中存在的問題、解決方法以及優化策略展開，強調了TRAINING-TESTING不一致現象對模型性能的影響。

## 主要觀念
1. **TRANSFORMER架構**：
   - **ENCODER**：負責將輸入序列轉換為 setHidden states。
   - **DECODER**：基於ENCODER的 setHidden states生成輸出序列。
   
2. **訓練過程中存在的問題**：
   - **EXPOSURE BIAS**：訓練時DECODER只接觸正確輸出，導致測試時對錯誤輸入反應不佳。
   - **BLEU SCORE**：雖然用於評估模型性能，但無法直接用作LOSSFUNCTION進行微分。

## 問題原因
1. **EXPOSURE BIAS**：
   - 因為DECODER在訓練時只接觸到正確的輸出，在測試時遇到錯誤輸入會導致模型性能下降。
   
2. **BLEU SCORE作為LOSS FUNCTION的局限性**：
   - BLEU SCORE需要計算兩個句子之間的相似度，無法直接進行微分，因此不能用於梯度下降算法。

## 解決方法
1. **強化學習（REINFORCEMENT LEARNING, RL）**：
   - 將BLEU SCORE作為獎勵信號，將DECODER視為AGENT，在RL框架下訓練模型。
   
2. **Scheduled Sampling**：
   - 在訓練過程中有計劃地引入錯誤的輸入，以提高模型在測試時的 robustness。

## 優化方式
1. **LOSSFUNCTION設計**：
   - 使用可微分的LOSSFUNCTION（如CROSSENTROPY）代替BLEU SCORE進行訓練。
   
2. **Training Technique**：
   - 通過Scheduled Sampling技術，在訓練過程中有計劃地引入錯誤輸入，模擬測試環境，提高模型的泛化能力。

##結論
TRANSFORMER模型在自然語言處理任務中表現優越，但在訓練和測試過程中存在不一致問題。通過強化學習和Scheduled Sampling等方法可以有效解決這些問題，提升模型性能。
</details>

<details>
<summary>315. [2021-04-09] 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (一) – 基本概念介紹</summary><br>

<a href="https://www.youtube.com/watch?v=4OWp0wDu6Xw" target="_blank">
    <img src="https://img.youtube.com/vi/4OWp0wDu6Xw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (一) – 基本概念介紹

# 文章整理：生成對抗網路（GAN）的核心概念與應用

## 1. 核心主題
- **生成對抗網路（GAN）**  
  GAN 是一種深度學習模型，由Ian Goodfellow等人於2014年提出，主要用於生成逼真的數據樣本，如圖像、音頻等。

## 2. 主要觀念
- **結構組成**  
  GAN 由兩個神經網路競爭對抗：  
  - **生成器（Generator）**：學習如何將低維向量映射到高維數據空間，以生成新的數據樣本。  
  - **判別器（Discriminator）**：用於區分真實數據和生成數據，提供反饋給生成器以改進性能。

- **訓練機制**  
  GAN 的訓練目標是最小化生成器被判別器識破的風險，通過交替更新生成器和判別器的參數來實現對抗均衡。

## 3. 問題原因
- **早期GAN的局限性**  
  - 生成圖片質量粗糙，存在模式坍塌問題。  
  - 訓練過程不穩定，易於梯度消失或爆炸。

## 4. 解決方法
- **改進的GAN架構**  
  - **Progressive GAN (ProGAN)**：通過逐步增加網路深度和分辨率，提升生成圖片的質量。  
  - **StyleGAN**：引入風格向量化概念，實現更高品質的圖像生成。  

- **訓練技巧**  
  - 使用 Wasserstein 情況（WGAN）改進損失函數，穩定訓練過程。  
  - 引入標籤指引（ conditional GAN, cGAN），讓生成器根據特定條件（如圖片類別）生成數據。

## 5. 優化方式
- **多領域對抗訓練**  
  - 設計多個判別器或生成器，提升模型的泛化能力。  

- **深度網路架構優化**  
  - 使用更深的網路結構（如殘差網絡）來增強表示能力。  

## 6. 應用案例
- **圖像生成**  
  - 動漫角色臉孔合成與風格轉移。  
  - 高清人臉生成，實現以假亂真效果。  

- **風格控制**  
  - 通過向量插值（interpolation）實現連續的面孔變化，如改變表情、姿勢等。  

## 7. 結論
GAN 技術已成為人工智慧領域的重要工具，其應用涵蓋圖像生成、數據增強、風格轉移等多個方面。未來隨著網路架構和訓練方法的進一步優化，GAN 將在更多領域實現更為複雜和自然的數據生成能力。

---

### 參考文獻
- Goodfellow, I., Pouget-Abadie, J., Mirza, M., & Bengio, Y. (2014). Generative adversarial nets. In *Advances in neural information processing systems* (pp. 2672-2680).
</details>

<details>
<summary>316. [2021-04-09] 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (二) – 理論介紹與WGAN</summary><br>

<a href="https://www.youtube.com/watch?v=jNY1WBb8l4U" target="_blank">
    <img src="https://img.youtube.com/vi/jNY1WBb8l4U/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (二) – 理論介紹與WGAN

# 文章重點整理

## 核心主題
本文主要探討深度學習中生成對抗網絡（GAN）的 Wasserstein 搮度 （Wasserstein GAN, WGAN）及其改進方法。文章圍繞 WGAN 的理論基礎、實現挑戰以及優化方案展開，旨在提供一個清晰的理解框架。

## 主要觀念
1. **Wasserstein Distance**：介紹了 Wasserstein 距離作為衡量兩個概率分佈之間相似性的度量標準，相比 Jensen-Shannon Divergence，Wasserstein 搮度 更能捕捉數據分布的細微差異。
2. **GAN 的局限性**：指出傳統 GAN 在訓練過程中易於出現梯度消失等問題，限制了生成器性能的提升。
3. **WGAN 的優勢**：強調 WGAN 通過引入 Wasserstein 距離，能夠有效解決上述問題，為模型提供更穩定的梯度信息。

## 問題原因
1. **傳統 GAN 的缺陷**：traditional GAN 在訓練過程中，判別器和生成器之間存在權力鬥爭，導致訓練不穩定。
2. **梯度消失問題**：判別器在傳統GAN中易於學習到與生成器分佈完全不同的數據，造成梯度信號微弱，限制了生成器的優化。

## 解決方法
1. **Wasserstein GAN (WGAN)**：
   - 通過引入 Wasserstein 距離作為損失函數，為模型提供更穩定和有信息量的梯度。
   - 強制要求判別器成為 1-Lipschitz 函數，以限制其輸出範圍，確保模型訓練的穩定性。

2. **Improved WGAN**：
   - 確保判別器符合 1-Lipschitz 函數的條件，避免梯度信號消失。
   - 引入 Gradient Penalty（梯度懲罰）方法，強制判別器在數據分佈之間平滑過渡。

3. **Spectral Normalization**：
   - 提出_spectrum 正規化技術，通過限制判別器的 spectral radius，確保其輸出範圍可控，進一步提升模型穩定性。

## 優化方式
1. **Gradient Penalty**：在Improved WGAN中引入梯度懲罰項，確保判別器輸出平滑，避免數據分佈之間的突兀變化。
2. **Spectral Normalization**：通過限制判別器的 spectral radius，進一步穩定模型訓練過程。

## 結論
Wasserstein GAN 及其改進方法為深度學習中的生成對抗網絡提供了更有效的訓練框架。引入 Wasserstein 距離和 1-Lipschitz 函數 constraint，顯著提升了 GAN 的性能和訓練穩定性。未來的研究可以進一步探索 spectral normalization 等技術，以期在更多實際應用中取得更好的效果。

# 文章關鍵詞
- 深度學習
- 生成對抗網絡（GAN）
- Wasserstein 距離
- WGAN
- 1-Lipschitz 函數
- Gradient Penalty
- Spectral Normalization
</details>

<details>
<summary>317. [2021-04-09] [ML 2021 (English version)] Lecture 6: What to do when optimization fails? (3/4)</summary><br>

<a href="https://www.youtube.com/watch?v=8yf-tU7zm7w" target="_blank">
    <img src="https://img.youtube.com/vi/8yf-tU7zm7w/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 6: What to do when optimization fails? (3/4)

### 核心主題  
- 文章主要探討機器學習中的優化方法及其進化過程，特別是針對錯誤曲面崎嶇導致的訓練瓶頹問題。  

### 主要觀念  
- **錯誤曲面特性**：深度學習模型的錯誤曲面通常具有多峽谷、高維度和非凸性質，這使得傳統最速下降法效果不佳。  
- **優化方法演進**：從基本的「樸素梯度下降」（Vanilla Gradient Descent）到現代的高度工程化的optimizer，如Adam及其變體，經歷了多階段的改進。  

### 問題原因  
- 傳統梯度下降法在面對高維、非凸錯誤曲面時，容易陷入局部最優或訓練慢。  
- 梯度震盪和方向不穩定性導致收斂困難。  

### 解決方法  
1. **動量法（Momentum）**：通過累積過去梯度的方向信息，加速收斂並跳過淺坑。  
2. **自適應學習率調控（Adaptive Learning Rate）**：利用梯度的二階統計信息（如方差）來自適應調整更新步長。  

### 優化方式  
1. **Adam優化器**：結合動量和自適應學習率調控，實現在複雜錯誤曲面上的有效探索。  
2. **Warm-Up技術**：在訓練初期降低.learning rate以穩定梯度 estimates，後期逐步升高以加速 convergence。  

### 其他進階內容  
- 各類optimizer的差異主要來自家動矩（M）和二階統計量（σ）的計算方法不同。  
- 學生若有興趣可進一步參閱教學助教錄製的優化相關影片，深入理解各種.optimizer的詳細原理。  

### 結論  
- 優化方法的進化體現了研究者對錯誤曲面特性逐步認識的深化，以及為克服訓練瓶頸而做出的多方面努力。  
- 現代optimizer如Adam已成為深度學習中的標準工具，但仍有大量改進空間和研究方向。
</details>

<details>
<summary>318. [2021-04-09] [ML 2021 (English version)] Lecture 11: Self-attention (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=zeCDPYZli0k" target="_blank">
    <img src="https://img.youtube.com/vi/zeCDPYZli0k/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 11: Self-attention (2/2)

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
</details>

<details>
<summary>319. [ML 2021 (English version)] Lecture 7: What to do when optimization fails? (4/4)</summary><br>

<a href="https://www.youtube.com/watch?v=t3u3WshJQV8" target="_blank">
    <img src="https://img.youtube.com/vi/t3u3WshJQV8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 7: What to do when optimization fails? (4/4)


</details>

<details>
<summary>320. [ML 2021 (English version)] Lecture 12: Transformer (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=zmOuJkH9l9M" target="_blank">
    <img src="https://img.youtube.com/vi/zmOuJkH9l9M/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 12: Transformer (1/2)


</details>

<details>
<summary>321. [ML 2021 (English version)] Lecture 13: Transformer (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=fPTj5Zh1ACo" target="_blank">
    <img src="https://img.youtube.com/vi/fPTj5Zh1ACo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 13: Transformer (2/2)


</details>

<details>
<summary>322. [ML 2021 (English version)] Lecture 14:  Generative Adversarial Network (GAN) (1/4)</summary><br>

<a href="https://www.youtube.com/watch?v=Mb9kddLfLRI" target="_blank">
    <img src="https://img.youtube.com/vi/Mb9kddLfLRI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 14:  Generative Adversarial Network (GAN) (1/4)


</details>

<details>
<summary>323. [ML 2021 (English version)] Lecture 15:  Generative Adversarial Network (GAN) (2/4)</summary><br>

<a href="https://www.youtube.com/watch?v=kFhv1I_fbZI" target="_blank">
    <img src="https://img.youtube.com/vi/kFhv1I_fbZI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 15:  Generative Adversarial Network (GAN) (2/4)


</details>

<details>
<summary>324. 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (三) – 生成器效能評估與條件式生成</summary><br>

<a href="https://www.youtube.com/watch?v=MP0BnVH2yOo" target="_blank">
    <img src="https://img.youtube.com/vi/MP0BnVH2yOo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (三) – 生成器效能評估與條件式生成


</details>

<details>
<summary>325. 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (四) – Cycle GAN</summary><br>

<a href="https://www.youtube.com/watch?v=wulqhgnDr7E" target="_blank">
    <img src="https://img.youtube.com/vi/wulqhgnDr7E/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】生成式對抗網路 (Generative Adversarial Network, GAN) (四) – Cycle GAN


</details>

<details>
<summary>326. 【機器學習2021】自督導式學習 (Self-supervised Learning) (一) – 芝麻街與進擊的巨人</summary><br>

<a href="https://www.youtube.com/watch?v=e422eloJ0W4" target="_blank">
    <img src="https://img.youtube.com/vi/e422eloJ0W4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自督導式學習 (Self-supervised Learning) (一) – 芝麻街與進擊的巨人


</details>

<details>
<summary>327. 【機器學習2021】自督導式學習 (Self-supervised Learning) (二) – BERT簡介</summary><br>

<a href="https://www.youtube.com/watch?v=gh0hewYkjgo" target="_blank">
    <img src="https://img.youtube.com/vi/gh0hewYkjgo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自督導式學習 (Self-supervised Learning) (二) – BERT簡介


</details>

<details>
<summary>328. 【機器學習2021】自督導式學習 (Self-supervised Learning) (三) – BERT的奇聞軼事</summary><br>

<a href="https://www.youtube.com/watch?v=ExXA05i8DEQ" target="_blank">
    <img src="https://img.youtube.com/vi/ExXA05i8DEQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自督導式學習 (Self-supervised Learning) (三) – BERT的奇聞軼事


</details>

<details>
<summary>329. [ML 2021 (English version)] Lecture 19:  Self-supervised Learning (aka Foundation Model) (2/3)</summary><br>

<a href="https://www.youtube.com/watch?v=L-ZQ-6vKOxU" target="_blank">
    <img src="https://img.youtube.com/vi/L-ZQ-6vKOxU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 19:  Self-supervised Learning (aka Foundation Model) (2/3)


</details>

<details>
<summary>330. [ML 2021 (English version)] Lecture 18:  Self-supervised Learning (aka Foundation Model) (1/3)</summary><br>

<a href="https://www.youtube.com/watch?v=mEcVirwmrkA" target="_blank">
    <img src="https://img.youtube.com/vi/mEcVirwmrkA/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 18:  Self-supervised Learning (aka Foundation Model) (1/3)


</details>

<details>
<summary>331. [ML 2021 (English version)] Lecture 17:  Generative Adversarial Network (GAN) (4/4)</summary><br>

<a href="https://www.youtube.com/watch?v=6xRAiKAYPxU" target="_blank">
    <img src="https://img.youtube.com/vi/6xRAiKAYPxU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 17:  Generative Adversarial Network (GAN) (4/4)


</details>

<details>
<summary>332. [2021-04-23] [ML 2021 (English version)] Lecture 16:  Generative Adversarial Network (GAN) (3/4)</summary><br>

<a href="https://www.youtube.com/watch?v=XcAmPtMQqS8" target="_blank">
    <img src="https://img.youtube.com/vi/XcAmPtMQqS8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 16:  Generative Adversarial Network (GAN) (3/4)

### 1. 核心主題
   - Conditional GAN（條件生成對抗網路）的核心主題在於利用生成對抗網路來實現有條件的圖片生成。
   - 通過引入條件信息（如音頻、視頻 frames 等），GAN 可以根據輸入的條件生成相應的圖片或畫面。
   - Conditional GAN 在多個領域有廣泛的應用，包括圖像生成、音頻視覺化、動畫生成等。

### 2. 主要觀念
   - ** Conditional Information**: Conditional GAN 要求輸入條件信息（如音頻片段、視頻幀等），以便根據這些條件生成相應的圖片。
   - ** Paired Data**: 需要配對數據（如音頻與圖像配對），以便模型學習條件信息與目標圖像之間的映射關係。
   - ** Joint Training**: 模型需要聯合訓練，使其既能夠 fool discriminator，又能夠生成符合條件的圖片。
   - ** Realism and Imagination**: Conditional GAN 生成的圖片通常更加寫實，但過於imaginative（ creativity）的結果可能不符合實際需求。
   - ** Applications**: Conditional GAN 在音頻視覺化、動畫生成、_ports 復活等多個領域有重要作用。

### 3. 問題原因
   - ** Lack of Clear Mapping**: 在某些情況下，模型無法明確地將條件信息（如音頻）映射到目標圖像。
   - ** Over-Imaginative Results**: 基本上 pure GAN 可能生成過於imaginative 的圖片，不符合實際需求。
   - ** Limited Training Data**: 如果訓練數據不足或質量不高，模型的性能可能受限。
   - ** Difficulty in Aligning Audio and Visual Information**: 將音頻與視覺信息對齊是一項挑戰。
   - ** Challenges in Real-Time Applications**: Conditional GAN 在即時應用中可能存在計算資源需求過高的問題。

### 4. 解決方法
   - ** Joint Training of GAN and Supervised Learning**: 同時訓練GAN和監督學習模型，以平衡寫實和 creativity。
   - ** Fine-Tuning the Model**: 根據具體任務對模型進行微調，以提昇性能。
   - ** Using Paired Data**: 確保使用高質量的配對數據來訓練模型。
   - ** Incorporating Prior Knowledge**: 引入先驗知識（如物體的形狀、結構等）來指導生成過程。
   - ** Post-Processing Techniques**: 使用後處理技術（如超分辨率重建）來提昇生成圖片的質量。

### 5. 優化方式
   - ** Multimodal Training**: 結合多種模態的信息（如音頻、視頻、文本等）進行訓練，以提高模型的泛化能力。
   - ** Few-Shot Learning**: 在條件信息有限的情況下，採用Few-Shot Learning 方法來提昇模型性能。
   - ** Advanced Architectures**: 使用更先進的架構（如SAGAN、PSPGAN 等）來改進生成效果。
   - ** Regularization Techniques**: 通過常規化技術（如Dropout、Batch Normalization等）來防止過度擬合。
   - ** Evaluation Metrics**: 引入多種評價指標（如PSNR、SSIM、_fid 等）來全面評估模型性能。

### 6. 結論
   - Conditional GAN 是一種強大且靈活的模型，能夠在多個領域實現有條件的圖片生成。
   - 雖然 Conditional GAN 在寫實性和 creativity 之間存在 trade-off，但通過聯合訓練和引入先驗知識等方法可以有效提昇性能。
   - Conditional GAN 的未來研究方向包括進一步優化模型架構、拓寬應用範疇以及提升即時應用的可行性。
</details>

<details>
<summary>333. [2021-04-30] 【機器學習2021】自督導式學習 (Self-supervised Learning) (四) – GPT的野望</summary><br>

<a href="https://www.youtube.com/watch?v=WY_E0Sd4K80" target="_blank">
    <img src="https://img.youtube.com/vi/WY_E0Sd4K80/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自督導式學習 (Self-supervised Learning) (四) – GPT的野望

# 文章重點整理

## 核心主題
- 自監督學習（Self-Supervised Learning）在自然語言處理、語音和影像領域中的應用與影響。

## 主要觀念
1. **自監督學習的基本概念**：
   - 利用未標籤數據進行訓練，通過任務設計（如填空題、預測下一代令牌）來提取特徵。
2. **BERT和GPT的架構**：
   - BERT：基於transformer的雙向模型，擅長語義理解。
   - GPT：基於transformer的單向模型，擅長生成任務。
3. **自監督學習在語音和影像中的應用**：
   - 語音：語音版本的BERT和GPT，預測接下來的聲音片段或填空。
   - 影像：使用掩蓋策略進行像素級預測或其他高級任務。

## 問題原因
1. **數據標籤成本高昂**：
   - 監督學習依賴大量標籤數據，限制了模型訓練的可行性。
2. **語音處理缺乏統一基準**：
   - 與文字處理相比，語音領域缺乏一個通用的基準數據集來評估不同模型的性能。

## 解決方法
1. **自監督學習技術**：
   - 利用未標籤數據進行預訓練，降低對標籤數據的依賴。
2. **SUPERB數據集的開發**：
   - 採用SUPERB（Speech processing Universal PERFORMANCE Benchmark）作為語音領域的基準，涵蓋多個語音任務。

## 優化方式
1. **跨模態應用**：
   - 將自監督學習技術應用於不同數據類型（如文字、語音、影像），拓展其使用範圍。
2. **多任務聯合訓練**：
   - 在同一框架下整合多個任務，提升模型的泛化能力和效率。

## 結論
- 自監督學習在降低數據依賴、提升模型性能方面具有顯著優勢。
- 語音和影像領域仍需進一步研究和標準化，以充分發揮自監督學習的潛力。

---

# 全文摘要

本文探討了自監督學習（Self-Supervised Learning）在自然語言處理、語音和影像等多個計算機視覺與語言處理領域中的應用。文章首先介紹了BERT和GPT這兩種基於自監督_learning的模型，強調其在降低數據標籤成本方面的優勢。進一步地，文章闡述了自監督學習技術在語音和影像處理中的潛力，並提出了SUPERB數據集作為語音領域的通用基準，以評估不同模型在多個語音任務上的性能。最後，文章指出了未來研究的方向，包括跨模態應用和多任務聯合訓練，進一步拓展自監督_learning的應用範圍與效果。
</details>

<details>
<summary>334. [2021-04-30] 【機器學習2021】自編碼器 (Auto-encoder) (上) – 基本概念</summary><br>

<a href="https://www.youtube.com/watch?v=3oHlf8-J3Nc" target="_blank">
    <img src="https://img.youtube.com/vi/3oHlf8-J3Nc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自編碼器 (Auto-encoder) (上) – 基本概念

### 文章整理：自動編碼器（Auto-Encoder）的核心概念與變形

#### 核心主題
- 自動編碼器（Auto-Encoder, AE）是一種無監督學習模型，旨在學習數據的低維表示並重建原始數據。
- 其核心思想是通過(encoder-decoder)架構，將數據壓縮為.latent representation.，然後再解碼回原來的形式。

#### 主要觀念
1. **encoder-decoder 架構**：
   - **Encoder**：負責將輸入數據映射到-latent space.。
   - **Decoder**：負責從-latent space.重建原始數據。
2. **自動編碼器的目標**：
   - 最小化重建錯誤，即讓重建後的數據與原始數據儘可能相似。

#### 問題原因
- 傳統自動編碼器可能存在以下限制：
  - 缺乏對數據分布的充分建模能力。
  - 在某些情況下，簡單的架構可能導致表徵不足或過度擬合。
  - 需要額外的正則化來防止解碼器直接復製輸入數據。

#### 解決方法
1. **加雜訊的自動編碼器（De-noising Auto-Encoder, DAE）**：
   - **思想**：在訓練時，故意向輸入數據中加入雜訊，然後要求模型重建未加雜訊的原始數據。
   - **優點**：
     - 強迫模型學習更 robust 的表徵。
     - 鼓勵模型捕獲數據的主要特性而非噪音。
2. **變分自動編碼器（Variational Auto-Encoder, VAE）**：
   - **思想**：將問題轉換為概率建模，假設.latent variables. 分布符合某種先驗分布（如正態分布），並最大化似然。
   - **優點**：
     - 可以生成新的數據樣本。
     - 具備_proba density estimation_.能力。

#### 結論
- 自動編碼器是一種靈活且強大的模型，廣泛應用於多個領域，包括圖像處理、自然語言處理等。
- **De-noising Auto-Encoder** 和 **Variational Auto-Encoder** 是兩個重要的變形，分別在 robustness 和 generative 能力上提供了改進。

#### 其他優化方式
1. **深度自動編碼器（Deep Auto-Encoder）**：
   - 增加網絡深度，提高模型的表達能力。
2. **多任務學習**：
   - 在重建數據的同時，結合其他任務（如分類），提高模型的泛化能力。

---

以上整理涵蓋了文章的主要內容，強調了自動編碼器的核心概念、變形及其在不同應用中的優勢。
</details>

<details>
<summary>335. [2021-04-30] 【機器學習2021】來自人類的惡意攻擊 (Adversarial Attack) (上) – 基本概念</summary><br>

<a href="https://www.youtube.com/watch?v=xGQKhbjrFRk" target="_blank">
    <img src="https://img.youtube.com/vi/xGQKhbjrFRk/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】來自人類的惡意攻擊 (Adversarial Attack) (上) – 基本概念

# 文章整理：攻擊模型的優化與實現

## 1. 核心主題
本文主要探討深度神經網絡（DNN）在面對敵對攻擊時的脆弱性，並提出多種防禦策略和攻擊方法，以提升模型的魯棒性。

## 2. 主要觀念
- **敵對樣本攻擊**：敵對攻擊者通過微小的擾動使模型輸出錯誤結果。
- **.gradient-based 攻擊方法**：利用梯度信息進行攻擊是目前最有效的手段之一。
- **防禦策略**：包括限制擾動幅度、迭代攻擊和正規化技術等。

## 3. 問題原因
- 深度神經網絡對微小的輸入擾動高度敏感，導致其易受敵對攻擊影響。
- 常見的防禦方法往往只能應對簡單攻擊，難以抵抗更為複雜的迭代攻擊。

## 4. 解決方法
### 4.1 梯度上升法（Gradient Ascent）
- **原理**：利用損失函數的梯度信息，逐步增強敵對擾動，直至模型輸出錯誤結果。
- **優點**：直觀且實施簡單。

### 4.2 Fast Gradient Sign Method (FGSM)
- **原理**：在梯度方向上加入簽號（Sign）操作，限制擾動幅度為ε。
- **公式**：\( x_{adv} = x + \epsilon \cdot \text{sign}(\nabla_x \mathcal{L}) \)
- **優點**：實現簡單，攻擊效率高。

### 4.3 迭代FGSM（Iterative FGSM）
- **原理**：多次應用FGSM，逐步增強擾動幅度。
- **優化方式**：
  - 每次迭代限制擾動幅度，避免一次性過大。
  - 若擾動後超出規定範圍，則將其拉回最近的合法點。

## 5. 優化方式
### 5.1 限制擾動幅度（ε控制）
- **目的**：防止攻擊擾動過度幹預模型輸出。
- **實施**：在每次迭代中限制擾動大小，確保擾動幅度可控。

### 5.2 拉回機制（Clipping Mechanism）
- **目的**：避免擾動後超出規定範圍。
- **實施**：若擾動後的樣本超出預定範圍，則將其拉回最近的合法點。

## 6. 結論
- **核心發現**：迭代FGSM方法在限制擾動幅度和控制攻擊步驟的前提下，能有效突破Simple Baseline防禦。
- **未來方向**：進一步研究更高效的攻擊與防禦策略，提升模型魯棒性。

---

本文系統地介紹了敵對攻擊的基本原理及其優化方法，並通過具體的案例分析展示了如何在限制擾動幅度的前提下，實現有效的攻擊。這些方法為提升深度學習模型的安全性提供了重要的理論支撐和實踐參考。
</details>

<details>
<summary>336. [2021-04-30] 【機器學習2021】自編碼器 (Auto-encoder) (下) – 領結變聲器與更多應用</summary><br>

<a href="https://www.youtube.com/watch?v=JZvEzb5PV3U" target="_blank">
    <img src="https://img.youtube.com/vi/JZvEzb5PV3U/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】自編碼器 (Auto-encoder) (下) – 領結變聲器與更多應用

# 文章重點整理

## 小節一：核心主題
- **主題**：異常檢測（Anomaly Detection）
- **目的**：通過自自動編碼器（Autoencoder）技術來實現圖片級別的異常檢測。
- **方法**：利用Autoencoder學習正常數據的特徵，進而判別異常數據。

## 小節二：主要觀念
1. **自自動編碼器（Autoencoder）介紹**：
   - **結構**：由Encoder和Decoder兩部分組成。
   - **功能**：通過壓縮數據再重建原始數據來學習數據的特徵表示。
2. **異常檢測的基本原理**：
   - **正常數據**：在訓練時已見過，Autoencoder能有效重建。
   - **異常數據**：未在訓練中見到，重建效果較差，導致重建損失（Reconstruction Loss）增大。

## 小節三：問題原因
- **分類資料不平衡**：
  - 在現實應用中，正常數據遠多於異常數據。
  - 異常數據往往少且難以收集。
- **傳統分類方法的局限性**：
  - 傳統二元分類需要均衡的正反例數據。
  - One Class 分類問題：只有一類數據可用。

## 小節四：解決方法
1. **Autoencoder 的應用**：
   - 訓練Autoencoder學習正常數據的特徵。
   - 測試階段，通過重建損失判別異常。
2. **重建損失作為異常指標**：
   - 正常數據重建損失小。
   - 異常數據重建損失大。

## 小節五：優化方式
1. **選擇適當的Autoencoder架構**：
   - 根據數據特徵選擇適合的網絡結構（如卷積自自動編碼器）。
2. **增強模型泛化能力**：
   - 通過數據增廣、正則化等 técnیques提高模型 robustness。
3. **多樣化訓練資料**：
   - 確保訓練資料覆蓋正常數據的多樣性，減少過擬合風險。

## 小節六：結論
- **Autoencoder在異常檢測中的價值**：
  - 適用於One Class分類問題。
  - 在缺少異常數據的情況下仍能有效工作。
- **未來應用前景**：
  - 異常檢測技術廣泛應用於安全監控、金融 fraud detection 等領域。
  - Autoencoder 技術為這些應用提供了有效的工具。

---

本文圍繞Autoencoder在異常檢測中的應用展開，強調了其在處理不平衡數據和One Class分類問題上的優勢。
</details>

<details>
<summary>337. [2021-05-07] [ML 2021 (English version)] Lecture 22:  Auto-encoder (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=PsBHWq9KKqk" target="_blank">
    <img src="https://img.youtube.com/vi/PsBHWq9KKqk/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 22:  Auto-encoder (2/2)

### 小節歸納

#### 核心主題
- **異常檢測（Anomaly Detection）**：本文圍繞如何利用自動編解碼器（Auto-encoder）進行異常檢測展開討論。

#### 主要觀念
1. **自動編解碼器的工作原理**：
   - 自動編解碼器是一種深度學習模型，由編碼器和解碼器兩部分組成。
   - 編碼器將輸入數據壓縮為潛在表示（latent representation），解碼器再將其重建為原數據。

2. **異常檢測的挑戰**：
   - 一類分類問題：僅有正常數據而缺乏異常數據。
   - 異常數據通常數量少，且可能混雜在正常數據中。

3. **自動編解碼器在異常檢測中的應用**：
   - 利用正常數據訓練自動編解碼器，使其能夠重建正常數據。
   - 通過比較輸入數據與重建數據的差異（重建損失）來判別是否存在異常。

#### 問題原因
- 在實際應用中，收集大量異常數據往往比正常數據更具挑戰性且成本高昂。
- 異常數據通常數量少，難以直接用於訓練分類模型。

#### 解決方法
1. **自動編解碼器的優勢**：
   - 只需正常數據即可訓練模型，適合一類分類場景。
   - 通過重建損失來衡量數據的異常性，無需標籤數據。

2. **具體實現**：
   - 使用正常數據訓練自動編解碼器。
   - 測試階段，將待測數據輸入模型，計算其重建損失。
   - 若重建損失超過設定門檻，判定為異常數據。

#### 優化方式
- **多樣化數據增強**：在訓練階段，可以對正常數據進行多樣化的數據增強（如旋轉、裁剪等），以提高模型的泛化能力。
- **深度學習架構優化**：嘗試不同的自動編解碼器架構（如變分自 автом機VAE、生成對抗網絡GAN）來改進重建效果。

#### 結論
- 自動編解碼器是一種有效的異常檢測工具，特別適合於正常數據充足而異常數據 scarce 的場景。
- 雖然自動編解碼器在某些應用中可能需要進一步優化，但其無需異常數據標籤的特點使其成為一類分類問題的理想選擇。

---

### 全文摘要

本文探討了利用自動編解碼器（Auto-encoder）進行異常檢測的方法。文章首先介紹了自動編解碼器的基本工作原理，即通過編碼器將數據壓縮為潛在表示，再由解碼器重建原數據。接著，文章指出了異常檢測中的兩個主要挑戰：一是正常數據遠多於異常數據（一類分類問題），二是異常數據通常混雜在正常數據中，導致收集和識別困難。

為了解決這些挑戰，文章提出使用自動編解碼器來訓練正常數據，並通過計算輸入數據與重建數據的差異（重建損失）來判別是否存在異常。具體而言，只需將待測數據輸入已訓練好的模型，若重建損失超過設定門檻，即可判定為異常數據。文章進一步討論了自動編解碼器在實際應用中的優勢，例如無需異常數據標籤、適合一類分類問題等。

最後，文章指出雖然 automatic encoder 在某些方面仍需改進，但其無需異常數據的特點使其成為一類分類問題的理想工具。全文強調了自動編解碼器在異常檢測中的重要性及其廣泛應用潛力。
</details>

<details>
<summary>338. [2021-05-07] [ML 2021 (English version)] Lecture 23:  Adversarial Attack (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=xw6K4naFWFg" target="_blank">
    <img src="https://img.youtube.com/vi/xw6K4naFWFg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 23:  Adversarial Attack (1/2)

### 英文標題  
A Comprehensive Overview of Adversarial Attack Methods in Deep Learning  

### 中文摘要  
本文系統性地介紹了深度學習中對抗攻擊的核心主題、主要觀念、問題原因、解決方法及優化方式，並總結了相關結論。文章重點圍繞.gradient descent method和.fast gradient sign method (FGSM) 展開，探討了單次攻擊與多次迭代攻擊的差異及其在不同基線模型中的表現。

---

### 重點整理  

#### 核心主題  
1. **對抗攻擊在深度學習中的應用**：探討通過擾動資料來 fool 模型的可能性與方法。  
2. **梯度下降法（Gradient Descent Method）**：用於迭代更新參數以實現對抗攻擊的技術。  
3. **Fast Gradient Sign Method (FGSM)**：一種基於.gradient descent 的快速對抗攻擊方法，只需一次迭代即可完成攻擊。  

#### 主要觀念  
1. **梯度下降法的基本原理**：通過反覆更新參數來接近目標，是一種常見的最優化技術。  
2. **FGSM的核心思想**：基於梯度的方向簽號進行一次性更新，將擾動限制在特定範圍內（如 ε）。  
3. **對抗攻擊的目的**：使模型在受到微小擾動後產生錯誤分類，測試模型的魯棒性。  

#### 問題原因  
1. **簡單基線模型易受對抗攻擊**：如未經過充分訓練或缺乏防禦機制的模型，容易被 FGSM 等方法攻破。  
2. **多次迭代可能超出擾動範圍**：在多輪更新中，參數可能超出行為邊界（如 L∞ 球），影響攻擊的有效性。  

#### 解決方法  
1. **一擊必殺法（FGSM）**：一次性完成對抗攻擊，確保擾動範圍在可控之內。  
2. **迭代式 FGSM**：允許多輪更新，但需定期將參數拉回行為邊界以避免越界。  
3. **防禦機制**：如加入正則化、訓練時增強對抗樣本等方法，提升模型的 robustness。  

#### 優化方式  
1. **調整學習率（ε）**：根據具體場景調節擾動幅度，平衡攻擊效果與可感知性。  
2. **多輪迭代**：通過增加迭代次數來增強攻擊能力，但需注意邊界控制。  
3. **智能擾動設計**：基於模型特性設計更有針對性的擾動，提升攻擊成功率。  

#### 結論  
1. **FGSM的優勢**：快速、簡潔，適合用於簡單基線模型的攻擊測試。  
2. **迭代式 FGSM 的提升**：通過多次更新可進一步提升攻擊效果，但需注意邊界的控制與恢復。  
3. **未來研究方向**：探索更高效的對抗攻擊方法，並結合防禦技術提升模型的 robustness。  

---

### 總結  
本文系統性地介紹了深度學習中對抗攻擊的核心技術與方法，特別是.gradient descent method 和.FGSM 的原理、應用及優化方式。文章強調了在不同基線模型下，一擊必殺法與多次迭代法的差異，並提出了未來研究的方向。
</details>

<details>
<summary>339. [2021-05-07] [ML 2021 (English version)] Lecture 21:  Auto-encoder (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=E7wlA85RxcI" target="_blank">
    <img src="https://img.youtube.com/vi/E7wlA85RxcI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 21:  Auto-encoder (1/2)

### 核心主題
- 自動編碼器（Auto-Encoder）及其變體的研究與發展。

### 主要觀念
1. **自動編碼器的基本原理**：用於學習數據的表徵，通過編碼器將數據壓縮為潛在空間表示，再通過解碼器重建原始數據。
2. **去噪自動編碼器（Denoising Auto-Encoder）**：在編碼器輸入端加入噪聲，並要求解碼器恢復原始乾淨數據，從而學習去除噪聲的能力。

### 問題原因
- 早期研究中，受限玻耳茲曼機（Restricted Boltzmann Machine, RBM）被廣泛使用，但其複雜性限制了其實用性。
- RBM 的對稱編解碼器結構限制了模型的靈活性。

### 解決方法
1. **去噪自動編碼器**：通過添加噪聲來提高模型的魯棒性，並強迫模型學習更健壯的表徵。
2. **大型語言模型如BERT**：可以視作一種去噪自動編碼器，通過掩蔽詞令牌加入噪聲，並重建原始句子。

### 優化方式
- 棄對稱結構限制，改用更靈活的深度神經網絡架構。
- BERT等現代模型將自動編碼器與解碼器結合，提升表徵學習能力。

### 總結
- 自動編碼器是一種歷史悠久但重要性持續的研究方向。
- 去噪自動編碼器及其衍生物BERT展示了其在現代深度學習中的廣泛應用價值。
</details>

<details>
<summary>340. [2021-05-07] [ML 2021 (English version)] Lecture 20:  Self-supervised Learning (aka Foundation Model) (3/3)</summary><br>

<a href="https://www.youtube.com/watch?v=6sAf24QvJEY" target="_blank">
    <img src="https://img.youtube.com/vi/6sAf24QvJEY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 20:  Self-supervised Learning (aka Foundation Model) (3/3)

### 小節歸納

#### 核心主題  
- 自我監督學習（Self-Supervised Learning, SSL）在多模態數據（如文本、語音和圖像）中的應用。  

#### 主要觀念  
1. **自我監督學習的定義與核心思想**  
   - 自我監督學習是一種無監督學習方法，通過設計偽任務從未標注數據中提取有用的特徵。  
   - 常見於自然語言處理（NLP）領域，如BERT和GPT模型的訓練。  

2. **文本領域的應用**  
   - BERT模型：通過填空任務（Masked Language Model, MLM）學習上下文語義。  
   - GPT模型：預測下一步詞元，實現生成式語言模型。  

3. **語音領域的挑戰與進展**  
   - 語音BERT和GPT的實現：將文本模型的概念遷移至語音處理。  
   - 常用策略包括遮蔽語音信號片段並讓模型重複預測缺失部分，或預測下一音節。  

4. **圖像領域的探索**  
   - 對圖像進行旋轉分類、區域掩蔽等任務，提取多模態特徵。  

5. **SUPERBbenchmark的提出**  
   - 為語音處理領域提供一個綜合性的benchmark，涵蓋內容識別、說話人識別、語調分析和語義理解等功能。  

#### 問題原因  
1. **語音領域的限制**  
   - 相對於文本領域（如GLUE benchmark），語音處理缺乏統一的benchmark來評估模型性能。  

2. **多模態數據的複雜性**  
   - 語音數據包含內容、語調、語義等多方面信息，難以用單一任務全面評估模型能力。  

#### 解決方法  
1. **SUPERBbenchmark的設計與實現**  
   - 提供十個不同類型的任務，涵蓋語音處理的多個層面（內容識別、說話人特徵提取、語義分析等）。  
   - 統一評估標準，便於研究者比較不同模型性能。  

2. **工具包的開發**  
   - 提供一套包含多種自我監督學習模型和下遊任務的工具包，簡化研究流程。  

#### 優化方式  
1. **benchmark的持續更新與完善**  
   - 根據研究進展不斷增加新任務和數據集，提升benchmark的代表性和實用性。  

2. **跨模態對比研究**  
   - 探索文本、語音和圖像等不同模態之間的相互作用，提升多模態自我監督學習的效果。  

#### 結論  
- 自我監督學習在文本、語音和圖像等數據處理中顯示出巨大的潛力。  
- 通過設計綜合性benchmark（如SUPERB）和工具包，可以推動語音處理領域的研究進展。  
- 未來的研究方向包括多模態對比學習、benchmark的拓展以及實用化場景的探索。
</details>

<details>
<summary>341. [2021-05-07] 【機器學習2021】來自人類的惡意攻擊 (Adversarial Attack) (下) – 類神經網路能否躲過人類深不見底的惡意？</summary><br>

<a href="https://www.youtube.com/watch?v=z-Q9ia5H2Ig" target="_blank">
    <img src="https://img.youtube.com/vi/z-Q9ia5H2Ig/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】來自人類的惡意攻擊 (Adversarial Attack) (下) – 類神經網路能否躲過人類深不見底的惡意？

### 文章整理：深度學習模型的安全性與防護措施

#### 1. 核心主題
- **深度學習模型的脆弱性**：深度學習模型易受 adversarial examples（敵意樣本）攻擊。
- **攻擊與防禦的研究進展**：介紹了攻擊方法、防禦策略及其局限性。

#### 2. 主要觀念
- **Adversarial Examples 的定義**： специально crafted 的輸入數據，會導致深度學習模型產生錯誤的預測。
- **黑箱攻擊的可能性**：即使缺乏模型內部結構知識，也能成功發動攻擊。
- **防禦策略的重要性**：需研究有效的防禦方法以提升模型安全性。

#### 3. 問題原因
- **模型脆弱性**：
  - 深度學習模型在高維空間中對小擾動敏感。
  - 對 adversarial perturbations（敵意幹擾）缺乏魯棒性。
- **防禦挑戰**：
  - 已存在的防禦方法可能被新型攻擊繞過。
  - Adversarial Training 資源消耗大，限制其廣泛應用。

#### 4. 解決方法
- **防禦技術**：
  - **幹擾キャンセル（Interference Cancellation）**：移除輸入數據中的敵意幹擾。
  - **模型修復（Model Repairing）**：修正模型預測以抵禦攻擊。
  - **模型魯棒化（Robustification）**：改進模型結構或訓練方法以增強抗攻擊能力。
- **Adversarial Training**：
  - 從現有數據生成 adversarial examples，加入訓練集以增強模型 robustness。
  - 可視為一種資料增強技術，提升模型泛化能力。

#### 5. 優化方式
- **提高計算效率**：
  - 研究輕量級的防禦方法，降低資源消耗。
  - 探索「免費」的 Adversarial Training 技術，減輕計算負擔。
- **持續改進防禦策略**：
  - 不斷更新防禦算法以應對新興攻擊方式。
  - 加強模型結構改進，提升先天抗攻擊能力。

#### 6. 結論
- **研究現況**：攻擊與防禦方法仍在不斷演化，尚無最終勝負者。
- **未來展望**：
  - 需持續研發更高效的防禦技術。
  - 提升模型魯棒性為當前研究關鍵方向。

#### 7. 參考文獻
- **Adversarial Training For Free**：介紹了一種低計算成本的 Adversarial Training 方法，值得進一步探究。
</details>

<details>
<summary>342. [2021-05-07] 【機器學習2021】機器學習模型的可解釋性 (Explainable ML) (上) – 為什麼類神經網路可以正確分辨寶可夢和數碼寶貝呢？</summary><br>

<a href="https://www.youtube.com/watch?v=WQY85vaQfTI" target="_blank">
    <img src="https://img.youtube.com/vi/WQY85vaQfTI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】機器學習模型的可解釋性 (Explainable ML) (上) – 為什麼類神經網路可以正確分辨寶可夢和數碼寶貝呢？

### 文章整理：探索深度學習模型中的語音訊號處理特性

#### 核心主題
- **深度學習在語音訊號處理中的應用**  
  探索深度學習模型（如LSTM、CNN）在語音訊號處理中的特性，包括聲音特徵提取、雜訊濾除及語者辨識等方面。

#### 主要觀念
1. **語音訊號的深度學習模型分析**  
   - 模型能夠學習並提取語音內容的高層特徵。
   - 舉例：5層Bi-LSTM模型在語音辨識中的應用。

2. **語者特徵的去除與保留**  
   - 通過模型分析，發現某些層次可能抹去語者的聲音特徵，僅保留語音內容。

3. **雜訊處理特性**  
   - 模型在不同層次對雜訊（如鋼琴聲）的濾除能力不同。
   - 舉例：CNN未能有效濾除雜訊，而LSTM在某層開始濔除雜訊。

#### 問題原因
- **語者特徵的丟失**  
  在某些深度學習模型中，後續層次可能失去語者的聲音特性，導致無法分辨不同語者。

- **雜訊濾除不一致**  
  不同網路層次對雜訊的處理效果存在差異，需進一步研究其原因。

#### 解決方法
1. **.Layer-wise 分析法**  
   - 過模型各層輸出進行逐層分析，以了解特徵提取和變化的具體過程。

2. **多模態模型整合**  
   - 結合語音和其它模態數據（如文本），以提升模型對語者特徵的保留能力。

3. **優化網路架構**  
   - 根據分析結果調整網路結構，強化雜訊濾除能力。

#### 優化方式
1. **網路結構設計**  
   - 在關鍵層次引入特定模塊以保留語者特徵。

2. **數據增強技術**  
   - 使用多樣化的訓練數據，提升模型的魯棒性和泛化能力。

3. **反向分析法**  
   - 通過逆向工程了解模型如何處理和改變輸入信號。

#### 結論
- **深度學習模型的有效性**  
  深度學習模型在語音內容提取方面表現出色，但在語者特徵保留上仍有改進空間。

- **層次分析的重要性**  
  過逐層輸出分析可揭示模型特性，為網路優化提供方向。

- **未來研究方向**  
  探索更多方法以平衡語音內容提取和語者特徵保留，提升模型在複雜環境下的性能。
</details>

<details>
<summary>343. [2021-05-13] [ML 2021 (English version)] Lecture 24:  Adversarial Attack (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=kRmBiV2X810" target="_blank">
    <img src="https://img.youtube.com/vi/kRmBiV2X810/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 24:  Adversarial Attack (2/2)

# 文章重點整理

## 核心主題
- **深度學習模型的安全性**：探討深度學習模型在面對攻擊時的脆弱性以及防禦方法。

## 主要觀念
1. **模型的脆弱性**：
   - 深度學習模型易受 adversarial examples（敵對樣本）影響，導致分類錯誤。
   - 攻擊者可利用.gradient information（梯度資訊）生成不可見的幹擾，降低模型性能。

2. **攻擊方法**：
   - **白盒攻擊**：攻擊者擁有模型的所有詳細信息，可用於精確設計敵對樣本。
   - **黑盒攻擊**：攻擊者僅知道模型的輸出，仍能通過遷移學習等技術影響目標模型。

3. **防禦策略**：
   - **事前防禦（Preventative Defence）**：
     - **數據增強（Data Augmentation）**：增加訓練數據的多樣性，提升模型 robustness。
     - **敵對訓練（Adversarial Training）**：在訓練階段引入敵對樣本，增強模型的抗幹擾能力。
   - **事後防禦（Post-Training Defence）**：
     - **.Gradient Masking**：隱藏梯度資訊，防止攻擊者利用。
     - **模型壓縮與量化**：降低模型複雜性，增加攻擊難度。

## 問題原因
1. 深度學習模型的高維特徵表示使其易受敵對樣本影響。
2. 攻擊方法的多樣化和技術門檻低，導致防禦挑戰增大。

## 解決方法
1. **敵對訓練**：
   - 在訓練過程中生成並加入敵對樣本，增強模型的魯棒性。
   - 可視為一種高效的數據增強方法，同時降低過擬合風險。

2. **數據增強**：
   - 通過增加多樣化的訓練數據，提升模型的 generalization 能力。

3. **防禦技術**：
   - 隱藏梯度資訊（Gradient Masking）：防止攻擊者利用梯度信息生成敵對樣本。
   - 模型壓縮與量化：降低模型複雜性，增加攻擊成本和難度。

## 優化方式
1. **計算效率**：
   - 確保防禦方法在大型數據集上具備可擴展性。
   - 採用「免費的敵對訓練」等技術，降低計算資源消耗。

2. **攻擊與防禦的平衡**：
   - 持續研究新型防禦策略，應對不斷進化的攻擊技術。

## 結論
- 目前深度學習模型的攻擊與防禦方法仍在快速發展中，尚無明確勝負者。
- 防禦側需結合多種策略，提升模型的安全性。

---

### 總結與建議
1. **研究建議**：
   - 進一步探索敵對訓練和其他防禦技術的 combination，提升防禦效果。
   - 加強對黑盒攻擊的研究，提高模型在未知環境下的安全性。

2. **實踐建議**：
   - 在實際應用中結合數據增強和敵對訓練等方法，增強模型 robustness。
   - 定期更新模型和防禦策略，跟蹤最新研究成果，保持技術先進性。
</details>

<details>
<summary>344. [2021-05-13] [ML 2021 (English version)] Lecture 25: Explainable ML (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=4rVD1EOaAX4" target="_blank">
    <img src="https://img.youtube.com/vi/4rVD1EOaAX4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 25: Explainable ML (1/2)

### 文章重點整理

#### 核心主題
本文圍繞深度學習模型在聲音處理和信息提取方面的應用展開討論，探討了模型如何進行語音識別、聲紋消除以及噪音過濾等操作。文章強調通過後 처리模型（如TTS）來分析前處理模型的特性，從而揭示模型在特徵提取過程中的行為。

#### 主要觀念
1. **語音特徵提取**：深度學習模型（如Bi-Directional LSTM和CNN）能夠有效地提取語音內容的特徵，同時可能消除或改變某些非-content特徵（如說話人的聲音特徵）。
2. **聲紋消除**：文中通過示例展示了模型在多層處理後，能夠將不同說話人的語音轉化為相似的聲音，這表明模型可能在訓練過程中有意無意地去除了聲紋信息。
3. **噪音過濾**：研究表明，LSTM層在某些情況下可以有效去除信號中的噪音（如鋼琴噪音），而CNN層在此案例中未顯著發揮噪音過濾作用。

#### 問題原因
1. **信息損失**：深度學習模型在提取特徵時，可能不可避免地丟失了一些重要的非-content信息，如說話人的聲紋特徵。
2. **模型特性揭示不足**： traditional visualization和分析方法（如Hinton的 visulization）雖然有用，但缺乏交互性和深入的行為揭示。

#### 解決方法
1. **後處理模型分析**：通過使用TTS模型對前處理模型的特徵進行重建，可以有效分析前處理模型的信息保留情況，進而理解其特性。
2. **多層網絡分析**：通過分層分析（如CNN和LSTM的不同深度），能夠更好地理解每個層在信號處理中的作用。

#### 優化方式
1. **模型結構改進**：根據分析結果，可以對模型結構進行優化，例如強化某些層的噪音過濾能力或聲紋保留功能。
2. **特徵保留策略**：在模型設計階段，可以有意識地設置機制來保留或去除特定類型的信息（如選擇性地保留聲紋特徵）。

#### 結論
1. 深度學習模型在聲音信息處理方面展現出強大的能力，但其特性揭示和行為分析仍具挑戰性。
2. 使用後處理模型進行反向分析是一種有效的研究方法，能夠幫助理解前處理模型的特徵提取機制。
3. 分層網絡分析對於揭示各級層的信息處理特徵具有重要意義，未來的研究可以進一步探索如何通過這種方式來優化模型性能。
</details>

<details>
<summary>345. [2021-05-21] 【機器學習2021】概述領域自適應 (Domain Adaptation)</summary><br>

<a href="https://www.youtube.com/watch?v=Mnk_oUrgppM" target="_blank">
    <img src="https://img.youtube.com/vi/Mnk_oUrgppM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】概述領域自適應 (Domain Adaptation)

### 文章重點整理

#### 1. 核心主題
- **Domain Adaptation**：研究如何在數據分布不同的情況下，遷移學習模型以適應目標域（Target Domain）的任務。
- **Domain Generalization**：探討模型如何泛化到未知的多個領域。

#### 2. 主要觀念
- **數據分布差異性**：源域和目標域之間可能存在顯著的數據分布差異，導致模型在目標域上的性能下降。
- **無標籤數據處理**：在目標域缺乏標註的情況下，需要設計有效的遷移學習策略。
- **小樣本挑戰**：當目標域數據量極小時，傳統的遷移方法可能失效。

#### 3. 問題原因
- **領域差異**：源域和目標域之間的特徵分布、統計特性或標籤空間存在差異，導致模型無法直接適應。
- **標註稀缺性**：在目標域中獲取標註數據困難，限制了監督學習的效果。
- **小樣本問題**：極少量的目標域數據使得難以訓練有效的遷移模型。

#### 4. 解決方法
##### (1) 基於對抗訓練的Domain Adaptation
- **對抗網絡**：通過設計對抗網絡（GANs）來最小化源域和目標域之間的分布差異。
- **領域對齊**：利用判別器迫使生成器學習跨領域的共享特徵，實現特徵空間的對齊。

##### (2) 測試時間訓練（Testing Time Training, TTT）
- **小樣本處理**：針對目標域數據極少的情況，採用測試時微調的方法，通過少量樣本快速調整模型參數。
- **增量學習**：利用目標域的小樣本數據，在測試階段進行在線學習，提升模型適應性。

##### (3) 域泛化（Domain Generalization）
- **多領域訓練集**：構建包含多個領域的訓練數據集，使模型在訓練時自然學習到跨領域的特徵。
- **數據增強**：通過模擬不同域的數據分布，生成虛擬的多領域樣本，豐富訓練數據。

##### (4) 參數調節與模型優化
- **權重調整**：在遷移過程中，平衡領域對齊和任務損失的權重，避免過度適應判別器。
- **正則化技術**：引入適當的正則化方法，保持模型在不同域之間的泛化能力。

#### 5. 確保模型性能的關鍵因素
- **特徵空間設計**：確保學習到的特徵能夠有效區分類別，同時保持跨域一致性。
- **領域對齊策略**：採用多種對齊方法（如對抗訓練、統計距離最小化）優化特徵分布。
- **泛化能力驗證**：通過在多個未知領域的測試驗證模型的泛化性能。

#### 6. 研究展望
- **複雜領域適應**：探索更高效的算法，應對更加複雜的領域差異和數據稀疏性問題。
- **多任務學習結合**：研究如何將域適應與多任務學習相結合，提升模型的整體表現。
- **實時應用優化**：針對實時應用場景，設計輕量級的遷移學習解決方案。

#### 7. 結論
- **技術可行性**：通過對抗訓練和測試時間微調等方法，能夠在一定程度上解決領域適配問題。
- **研究必要性**：域適應和泛化技術對於實際應用中的模型部署至關重要，特別是在標註數據稀缺或領域分布多變的情況下。
</details>

<details>
<summary>346. [2021-05-21] 【機器學習2021】機器學習模型的可解釋性 (Explainable ML) (下) –機器心中的貓長什麼樣子？</summary><br>

<a href="https://www.youtube.com/watch?v=0ayIPqbdHYQ" target="_blank">
    <img src="https://img.youtube.com/vi/0ayIPqbdHYQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】機器學習模型的可解釋性 (Explainable ML) (下) –機器心中的貓長什麼樣子？

### 小節一：核心主題  
- 本文圍繞**可解釋機器學習（Explainable Machine Learning）**展開討論，探討如何提高模型決策過程的透明性和可解釋性。  

### 小節二：主要觀念  
1. **機器學習模型的黑箱問題**：  
   - 深度學習模型（如神經網絡）因其複雜性而被視為「黑箱」，其決策過程不易被人理解。  
2. **可解釋性的重要性**：  
   - 可解釋性在模型的信任、驗證和改進中具有關鍵作用，尤其是在醫學、金融等高風險領域。  
3. **提升可解釋性的方法**：  
   - 使用簡單的模型（如線性模型）或對黑箱模型進行後處理解讀。  

### 小節三：問題原因  
- 神經網絡等複雜模型的決策機制缺乏透明度，導致用戶難以信任和驗證模型的行為。  
- 模型易受敵對攻擊（Adversarial Attacks）影響，進一步暴露其脆弱性。  

### 小節四：解決方法  
1. **後處理解讀技術**：  
   - 使用簡單的模型（如LASSO、 Ridge Regression）對黑箱模型的決策進行局部解讀。  
2. **局部可解釋性模型**：  
   - 引入**LIME（Local Interpretable Model-agnostic Explanations）**等方法，通過在小數據範圍內訓練線性模型來模擬黑箱模型的行為，從而提供局部解讀。  
3. **增設額外類別**：  
   - 在分類器中增加「都不是」的選項，並最小化其機率，以降低模型錯誤分類的風險。  

### 小節五：優化方式  
1. **整合多種解釋方法**：  
   - 結合全局和局部解讀技術，提供更全面的模型行為分析。  
2. **提升模型 robustness**：  
   - 遷移學習、數據增強等技術可提高模型對敵對攻擊的抵抗能力。  

### 小節六：結論  
- 可解釋性是機器學習模型可信度的重要指標，需通過多種技術手段（如LIME）來提升模型的透明性與用戶信任。  
- 增設額外類別並最小化其機率可在一定程度上降低錯誤分類風險，但仍需進一步實驗驗證其效果。
</details>

<details>
<summary>347. [2021-05-22] 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (一) – 增強式學習跟機器學習一樣都是三個步驟</summary><br>

<a href="https://www.youtube.com/watch?v=XWukX-ayIrs" target="_blank">
    <img src="https://img.youtube.com/vi/XWukX-ayIrs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (一) – 增強式學習跟機器學習一樣都是三個步驟

### 文章重點整理

#### 核心主題
本文主要探討如何訓練一個.Actor*（代理）來執行符合特定期望的行為，通過定義適當的損失函數和訓練數據來實現此目標。

---

#### 主要觀念

1. **Actor 的訓練模式**  
   - Actor 的訓練類似於監督學習（Supervised Learning），其中訓練數據包含狀態（State, s）和對應動作（Action, a）的配對。
   - 每個動作可以被分為兩種類型：
     - **期望執行的動作**：用 +1 表示。
     - **不期望執行的動作**：用 -1 表示。

2. **訓練數據的定義**  
   - 訓練數據由一系列（s, a）配對組成，其中 s 是環境中的狀態，a 是在該狀態下期望Actor採取的行動。
   - 每個動作可以具有不同的權重（如 +1.5 或 +0.5），表示不同程度的執行期望。

3. **損失函數的定義**  
   - 使用交叉熵損失（Cross-Entropy Loss）來衡量.Actor*的預測行動與實際期望行動之間的差異。
   - 損失函數的形式為：
     \[
     L = -\sum_{i=1}^{N} w_i \cdot y_i \cdot \log(\hat{y}_i) + (1 - y_i) \cdot \log(1 - \hat{y}_i)
     \]
     其中，\(w_i\) 表示第 i 筆數據的權重，\(y_i\) 是期望行動（+1 或 -1），\(\hat{y}_i\) 是.Actor*預測的概率。

---

#### 問題原因

1. **訓練數據的來源**  
   - 如何有效收集和定義訓練數據，以確保Actor在各種狀態下能夠執行正確的行動。
   - 經驗表明，直接定義訓練數據可能具有挑戰性，特別是對於複雜環境。

2. **損失函數的優化**  
   - 損失函數需要能夠反映不同程度的行動期望，以便Actor在訓練過程中學會區分重要和次要的行動。

---

#### 解決方法

1. **訓練數據的生成**  
   - 通過專家示範或模擬環境來收集training data。
   - 確定每個狀態下Actor應該執行的行動，並為其分配適當的權重。

2. **損失函數的設計**  
   - 在交叉熵損失中引入權重因子 \(w_i\)，以反映不同行動的重要程度。
   - 通過反向傳播（Backpropagation）來優化.Actor*的參數θ，最小化損失函數。

---

#### 優化方式

1. **動機設計**  
   - 給予Actor執行某些行動更高的權重，以強調這些行動的重要性。
   - 例如，在特定狀態下，Actor應該避免某個有害行動，可以給予該行動的權重為-2，以增強訓練效果。

2. **分級期望**  
   - 根據不同行動的影響程度，將其分級（如高、中、低），並在損失函數中體現這些差異。
   - 這可以幫助.Actor*在訓練過程中更精準地掌握各類行動的執行策略。

---

#### 結論

本文提出了一種基於監督學習的.Actor*訓練方法，通過定義具體的訓練數據和損失函數，使得Actor能夠學習到符合期望的行為。核心思想是將行動期望轉化為交叉熵損失中的權重因子，並通過反向傳播優化.Actor*的參數。此方法為Actor在複雜環境下的行為控制提供了一種可行的途徑，但仍需進一步研究如何高效收集和定義訓練數據，以提高訓練效果。
</details>

<details>
<summary>348. [2021-05-22] 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (二) – Policy Gradient 與修課心情</summary><br>

<a href="https://www.youtube.com/watch?v=US8DFaAZcp4" target="_blank">
    <img src="https://img.youtube.com/vi/US8DFaAZcp4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (二) – Policy Gradient 與修課心情

### 一、核心主題：強化學習（Reinforcement Learning）中的策略優化方法

1. **主要焦點**：
   - 探討在強化學習中如何通過策略優化方法提升智能體的行爲表現。
   - 強調策略優化的核心思想及其在實際應用中的重要性。

2. **核心概念**：
   - 策略（Policy）：定義了智能體在給定狀態下的行爲選擇規則。
   - 獎勵信號（Reward Signal）：用於評估智能體行爲的優劣，指導學習過程。
   - 探索與利用（Exploration vs. Exploitation）：平衡新舊行爲選擇以確保有效學習。

### 二、主要觀念：策略優化的基本原理

1. **基本原理**：
   - 策略優化的目標是通過迭代更新策略，使得智能體在環境中獲得的累積獎勵最大化。
   - 每次迭代中，智能體會與環境交互，收集經驗並根據反饋調整行爲。

2. **關鍵步驟**：
   - 行爲選擇：基於當前策略生成動作。
   - 反饋接收：從環境中獲取獎勵信號。
   - 策略更新：利用反饋優化策略參數。

### 三、問題原因：傳統策略優化方法的局限性

1. **主要挑戰**：
   - **探索不足**：初始策略可能過於固定，缺乏多樣性，導致無法充分探索狀態空間。
   - **梯度估算偏差**：直接優化策略可能導致梯度估計不穩定或偏離最優解。
   - **樣本效率低下**：傳統方法需要大量交互才能收斂，限制了在複雜環境中的應用。

2. **具體問題**：
   - 策略更新過程中可能陷入局部最優。
   - 高維狀態空間和動作空間增加了學習難度。
   - 動作選擇的隨機性不足可能導致智能體無法發現最佳行爲路徑。

### 四、解決方法：PPO（Proximal Policy Optimization）算法

1. **基本思想**：
   - 通過限制策略更新的幅度，確保每次迭代中策略的變化量在合理範圍內。
   - 分離舊策略和新策略的概率分布，利用比值估計法優化目標函數。

2. **具體實現**：
   - 引入兩個概率比值（old policy 和 new policy）來計算損失函數。
   - 通過限制策略更新的幅度（clip parameter）防止參數更新過大導致性能下降。
   - 利用信任區域方法確保每次更新穩定可靠。

3. **優點**：
   - 算法穩定性高，收斂速度快。
   - 具有良好的樣本效率，在複雜環境中表現優異。
   - 易於實現且具有較強的理論基礎支持。

### 五、優化方式：提升策略探索的有效性

1. **增加動作隨機性**：
   - 在策略輸出中引入熵正則化（Entropy Regularization），鼓勵智能體嘗試更多動作，避免過早收斂。
   - 在策略參數更新過程中添加噪聲，增強探索能力。

2. **經驗重放（Experience Replay）**：
   - 通過回放歷史經驗，增加訓練數據的多樣性，提升學習效率。

3. **多-threaded exploration**：
   - 利用多線程或多進程同時進行環境交互和策略優化，加速學習過程。

### 六、結論與未來方向

1. **研究結論**：
   - PPO算法在強化學習領域展現了顯著優勢，特別是在複雜任務中表現優異。
   - 策略優化的關鍵在於平衡探索與利用，有效提升智能體的學習效率和性能。

2. **未來方向**：
   - 探索更高效的梯度估算方法，進一步提高樣本利用率。
   - 研究更加魯棒的策略更新機制，增強算法在不同環境中的適應性。
   - 結合其他機器學習技術（如深度神經網絡、圖結構學習等），拓展強化學習的應用範圍。

3. **實際應用**：
   - 在機器人控制、遊戲AI、自動駕駛等領域具有廣泛前景。
   - 通過不斷優化策略優化方法，推動人工智能技術的進一步發展。
</details>

<details>
<summary>349. [2021-05-26] [ML 2021 (English version)] Lecture 26: Explainable ML (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=5VPy7OGlGMQ" target="_blank">
    <img src="https://img.youtube.com/vi/5VPy7OGlGMQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 26: Explainable ML (2/2)

### 核心主題
- **解釋性機器學習**：探討如何使機器學習模型更加透明和易於理解。

---

### 主要觀念
1. **可解釋性的重要性**：
   - 機器學習模型的決策過程需要被人類理解和信任。
   - 特別是在醫療、金融等高風險領域，可解釋性至關重要。

2. **黑箱問題**：
   - 現代深度學習模型（如神經網路）通常被視為「黑箱」，其內部運作機制不易理解。

3. **對抗攻擊與可靠性**：
   - 機器學習模型可能受到對抗攻擊，導致錯誤的決策。
   - 提高可解釋性有助於增強模型的可靠性和抗幹預能力。

---

### 問題原因
1. **模型複雜性**：
   - 神經網路等深度 learning模型結構複雜，導致其運作機制不易解讀。

2. **缺乏透明度**：
   - 黑箱模型的決策缺乏明確的解釋，影響用戶的信任和應用。

3. **對抗攻擊的挑戰**：
   - 模型可能被設計外的輸入操縱，導致不可預測的行為。

---

### 解決方法
1. **局部可解釋性方法**：
   - 使用如 LIME（Local Interpretable Model-Agnostic Explanations）等技術，僅解析模型在特定區域的行爲。
   - 通過簡單的線性模型模擬小範圍的黑箱行為來提供解釋。

2. ** adversarial attacks 的防禦**：
   - 增加額外的分類選項（如「非上述任何一類」），以降低模型錯誤分類的可能性。
   - 通過數據增強和正則化技術提高模型魯棒性。

3. **模型簡化與可視化**：
   - 使用線性模型或其他簡單模型來近似黑箱模型的行為。
   - 通過可視化工具展示模型決策的關鍵特徵。

---

### 優化方式
1. **多分類策略**：
   - 添加額外的分類選項（如「非上述任何一類」），以提高模型的可靠性和解釋性。

2. **混合模型設計**：
   - 結合深度學習模型和簡單模型，利用深度模型的強大能力和簡單模型的可解讀性。

3. **持續研究與實驗**：
   - 從事更多的實驗來驗證不同方法的效果，進一步優化解釋性機器學習技術。

---

### 總結
- 可解釋性是機器學習模型應用的重要條件。
- 地區性的可解釋性方法（如 LIME）和防禦對抗攻擊的策略（如添加額外分類選項）提供了有效的解決方案。
- 未來的研究需進一步探索如何平衡模型的複雜性和可解釋性，以實現更可靠的機器學習系統。
</details>

<details>
<summary>350. [2021-05-27] [ML 2021 (English version)] Lecture 28: Introduction of Reinforcement Learning (RL) (1/5)</summary><br>

<a href="https://www.youtube.com/watch?v=0oucZNfBXlI" target="_blank">
    <img src="https://img.youtube.com/vi/0oucZNfBXlI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 28: Introduction of Reinforcement Learning (RL) (1/5)

### 文章整理：基於監督學習的Actor訓練框架

#### 核心主題
- **Actor訓練的本質**：通過定義明確的行爲期望，利用監督學習方法訓練一個能夠執行預期動作的智能體（Actor）。

#### 主要觀念
1. **Actor的訓練目標**：
   - 使Actor在特定狀態下執行期望的動作。
   - 區分「應該執行」的動作和「不應該執行」的動作。

2. **行爲數據的表示**：
   - 每對狀態-動作（s, a）配對有一個評分（An），表示對該動作的期望程度。
   - 評分可以是正數（期望執行）、負數（不期望執行）或零（中立態度）。

3. **監督學習框架的應用**：
   - 將Actor訓練類比爲分類任務，狀態s被視爲輸入，動作a被視爲輸出標籤。
   - 使用交叉熵損失函數衡量預測與真實動作的差異。

4. **行爲評分的作用**：
   - 通過An調節不同狀態-動作對的權重，實現差異化的行爲管理。
   - 高正數評分表示強烈期望執行，低或負評分表示較低或完全不期望執行。

#### 問題原因
1. **數據來源的挑戰**：
   - 如何生成大量高質量的狀態-動作配對（s, a）作爲訓練數據？
   - 數據的質量直接影響Actor的學習效果。

2. **行爲評分的主觀性**：
   - 評分An需要明確定義，不同場景下的人爲主觀判斷可能影響模型性能。

3. **動態環境適應性**：
   - 在實際應用中，環境可能是動態變化的，固定訓練數據可能導致Actor在新環境中表現不佳。

#### 解決方法
1. **數據收集策略**：
   - 通過專家示範、模擬器生成或人機交互等方式收集狀態-動作配對。
   - 確保數據覆蓋不同狀態和動作的多樣性。

2. **評分機制的設計**：
   - 根據任務需求設計評分規則，明確每個狀態-動作對的期望程度。
   - 使用領域知識或專家意見來制定評分標準。

3. **模型優化與調整**：
   - 採用合適的監督學習算法（如隨機森林、神經網絡等）訓練Actor。
   - 調整模型參數以優化損失函數，提升預測準確性。

4. **動態適應機制**：
   - 引入強化學習或其他自適應方法，使Actor能夠根據環境反饋調整行爲。
   - 定期更新訓練數據和模型，以應對環境變化。

#### 結論
- 通過明確的行爲期望定義和監督學習框架，可以有效地訓練一個Actor來執行預期動作。
- 行爲評分機制提供了靈活的控制手段，可以根據具體需求調節不同狀態-動作對的重要性。
- 數據收集和評分機制的設計是Actor訓練的關鍵挑戰，需要結合領域知識和實際應用需求進行優化。
</details>


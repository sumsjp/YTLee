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
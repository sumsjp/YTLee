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
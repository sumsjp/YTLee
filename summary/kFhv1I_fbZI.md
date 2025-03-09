### 文章整理：Wasserstein GAN (WGAN) 的核心思想與進展

#### 1. 核心主題  
Wasserstein GAN (WGAN) 提出了一種基於 Wasserstein 距離的生成對抗網路框架，旨在解決傳統GAN 中存在的訓練不穩定和模式崩潰問題。其核心在於將生成模型與真實數據分布之間的距離度量改為 Wasserstein 距離，而非傳統的 Jensen-Shannon 散度。

#### 2. 主要觀念  
- **Wasserstein 距離**：WGAN 使用 Earth Mover's Distance (EMD) 或.TRANSPORTATION cost 來衡量兩個概率分布之間的相似性。這種距離具有良好的數學特性，能夠更好地捕捉數據分佈的細微差異。
- **Earth Mover's Distance (EMD)**：EMD 可以直觀地理解為將一個分佈的「土」搬到達另一個分佈的「坑」所需要的最小工作量，這在計算上可以高效求解。

#### 3. 問題原因  
- **Jensen-Shannon 散度的局限性**：傳統 GAN 基於 Jensen-Shannon (JS) 散度，但 JS 散度在數據分佈接近時會退化為常數，導致梯度消失問題。
- **訓練不穩定性**：JS散度的特性使得GAN在訓練晚期易於陷入振蕩或模式崩潰。

#### 4. 解決方法  
- **Wasserstein 距離作為損失函數**：WGAN 將生成器的損失函數改為 Wasserstein 距離，這避免了JS散度的退化問題。
- **限制判別器為1-Lipschitz函數**：為確保Wasserstein距離正確性，需要判別器D(x)滿足1-Lipschitz條件，即|D(x) - D(y)| ≤ |x - y|。

#### 5. 測試與實施挑戰  
- **限制判別器的實現**：最初WGAN直接限制判別器的輸出範圍，但不限於此方法無法完全保證1-Lipschitz性。
- **直觀上的局限性**：限制判別器的輸出可能影響其表達能力。

#### 6. 優化方式  
- **梯度懲罰（Gradient Penalty）**：在「Improved WGAN」中提出，通過添加梯度懲罰項來約束判別器的梯度 magnitude 維持在1附近。
- **光議規格化（Spectral Normalization）**：此方法限制判別器權重矩的 spectral radius 綴身為1，從而控制其梯度，有效實現1-Lipschitz性。

#### 7. 方法改進  
- **「Improved WGAN」**：引入梯度懲罰項，穩定訓練並提升生成效果。
- **「Improved The Improved WGAN」**：進一步優化 spectral normalization 方法，提高判別器的限制性與訓練穩定性。

#### 8. 結論  
Wasserstein GAN 系列方法通過改進損失函數和約束條件，顯著提升了生成模型的訓練穩定性和生成效果。其中，梯度懲罰和光議規格化等技術為後續GAN研究提供了重要參考。

---

### 參考文獻  
- Arjovsky, M., Chintala, S., & Bottou, L. (2017). Wasserstein GAN.
- Gulrajani, I., & al. (2017). Improved WGAN.
- Odena, A., & al. (2018). Improved The Improved WGAN.
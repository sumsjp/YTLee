### 小節一：Auto-Regressive Models 的特性與 challange
1. **核心主題**：
   - Auto-Regressive models 是按部就班地生成序列數據。
2. **主要觀念**：
   - 按照時間或空間順序逐步生成，每一步都基於前一步的輸出。
3. **問題原因**：
   - 品質較高但生成速度較慢。

### 小節二：Non-Auto-Regressive Models 的特性與 Challange
1. **核心主題**：
   - Non-Auto-Regressive models 是齊頭並進地生成數據。
2. **主要觀念**：
   - 同時生成整個序列或完整數據，不依賴前一步的輸出。
3. **問題原因**：
   - 生成速度快但品質可能較差。

### 小節三：Auto-Regressive 與 Non-Auto-Regressive 的結合
1. **核心主題**：
   - 結合兩種方法以優化生成效果和速度。
2. **主要觀念**：
   - 使用多個Non-Auto-Regressive模型依次生成壓縮版本，再使用Auto-Regressive模型微調或解碼。
3. **解決方法**：
   - 將Auto-Regressive部分替換為Non-Auto-Regressive的壓縮生成，提升速度。
4. **優化方式**：
   - 通過展示中間版本（如MidJourney）讓用戶看到生成過程。

### 小節四：現代影像生成模型的實踐
1. **核心主題**：
   - 現代影像生成AI多結合兩種方法。
2. **主要觀念**：
   - 使用多個Non-Auto-Regressive模型生成壓縮版本，再解碼為高品質影像。
3. **解決方法**：
   - 將非自回歸生成的中間結果過.decoder 以得到最終圖像。
4. **例子**：
   - MidJourney、Stable Diffusion、新版DALL-E。

### 小節五：結論
1. **核心主題**：
   - 結合Auto-Regressive和Non-Auto-Regressive模型是提升影像生成效率和品質的有效方式。
2. **主要觀念**：
   - 每種方法有其優缺點，結合使用可平衡速度與品質。
# 文章整理：Transformer模型及其訓練技巧

## 核心主題
- **Transformer模型**：文章圍繞Transformer模型的(encoder-decoder架構)展開討論，強調其在自然語言處理中的重要性。
- **訓練技術與挑戰**：探討了Transformer模型在訓練過程中面臨的主要問題及相應的解決方法。

## 主要觀念
1. **Encoder-Decoder架構**：
   - Transformer模型由(encoder和decoder)兩個主要部分組成，實現並行處理和高效的序列轉換。
2. **分詞級訓練與解碼器輸入不一致**：
   - 訓練過程中，解碼器接收的是正確的目標分詞，但在實際測試中，解碼器需要自行生成輸出，導致不一致。
3. **BLEU Score與Cross Entropy之間的差異**：
   - Cross Entropy作為訓練損失函數，而BLEU Score用於評估模型性能，兩者存在概念和計算上的不同。

## 問題原因
1. **Exposure Bias（敞露偏差）**：
   - 解碼器在訓練期間只接收到正確的答案，導致其在測試時遇到錯誤輸入時表現不佳。
2. **BLEU Score的不可微分性**：
   - BLEU Score的計算複雜且不可微分，限制了其直接用作損失函數進行優化。

## 解決方法
1. **強化學習（Reinforcement Learning, RL）**：
   - 將BLEU Score作為RL的獎勵函數，將解碼器視為AGENT，通過RL來優化模型性能。
2. **Scheduled Sampling（計劃抽樣）**：
   - 在訓練過程中有計劃地向解碼器提供錯誤的回答，以降低Exposure Bias的影響。

## 優化方式
1. **訓練與測試一致性**：
   - 通過引入計劃抽樣等技術，讓解碼器在訓練階段接觸到一些錯誤輸入，提高其在實際應用中的魯棒性。
2. **損失函數選擇**：
   - 雖然BLEU Score不可微分，但可以使用Cross Entropy作為訓練損失函數，並在測試階段用BLEU Score進行評估。

## 結論
- Transformer模型在自然語言處理中具有重要意義，但仍需面對訓練與測試不一致、BLEU Score不可優化等挑戰。
- 通過強化學習和計劃抽樣等技術，可以有效提升模型的性能和魯棒性。
- 儘管BLEU Score的使用存在限制，但結合Cross Entropy進行訓練仍是目前可行的方法。
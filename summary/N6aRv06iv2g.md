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
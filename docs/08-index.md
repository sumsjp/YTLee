<details>
<summary>448. [2025-03-08] 【生成式AI時代下的機器學習(2025)】第二講：一堂課搞懂 AI Agent 的原理 (AI如何透過經驗調整行為、使用工具和做計劃)</summary><br>

<a href="https://www.youtube.com/watch?v=M2Yg1kwPpts" target="_blank">
    <img src="https://img.youtube.com/vi/M2Yg1kwPpts/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

### 文章重點整理

#### 核心主題
- **人工智慧AGENT的規劃能力**：探討AIAGENT如何通過內部模擬（brain play or brain theater）來執行推理和規劃，以提升任務效能。

#### 主要觀念
1. **Brain-in-the-Middle (FITM) 模型**：
   - 這些模型能夠在內部模擬不同的行動路徑，評估可能的結果，從而做出最佳決策。
   - 內部模擬過程類似於人類的「腦內小劇場」，用來規劃和驗證行動方案。

2. **TREE SEARCH規劃方法**：
   - 通過樹狀結構探索所有可能的行動路徑，評估每一步的成功概率，最終選擇最優解。
   - 示例：積木堆疊問題中的四步規劃。

3. **REASONING能力**：
   - 具備推理能力的模型能在內部模擬多種可能性，從而做出更為智能的決策。
   - 模型如DeepSeek-R1展示了其在任務中的規劃和執行能力。

#### 問題與原因
1. **過度思考（Over Thinking）**：
   - 具備FITM的模型在某些情況下會陷入無限的內部模擬，導致行動遲緩或無法決定。
   - 雖然這些模型在規劃上表現優異，但在實際執行中可能因為過度推理而影響效率。

2. **行動力不足**：
   - 有些模型缺乏實驗精神，不敢輕易嘗試新策略，導致行動受限或提前放棄。

#### 解決方法
1. **行動導向的學習（Action-Driven Learning）**：
   - 鼓勵模型在某些情況下直接執行行動，而非一味模擬。
   - 示例：信用卡支付按鈕的點擊實驗。

2. **平衡推理與行動**：
   - 確保模型在內部模擬後及時將規劃轉化為實際行動，避免過度沉溺於模擬。
   - 強調「想」與「做」的均衡，以提升整體效率。

#### 健康建議
- **研究未來方向**：
  - 探索如何控制FITM模型的內部模擬程度，平衡其推理能力與行動力。
  - 研究如何設計模型，在適當時候切換至行動模式，避免過度思考。

#### 結論
- 具備FITM和REASONING能力的AIAGENT在規劃和執行複雜任務方面表現優越，但需警惕其「想太多」的問題。
- 未來研究應著重於如何平衡模型的內部模擬與實際行動，以提升其整體效能。
</details>

<details>
<summary>447. [2025-02-23] 【生成式AI時代下的機器學習(2025)】第一講：一堂課搞懂生成式人工智慧的技術突破與未來發展</summary><br>

<a href="https://www.youtube.com/watch?v=QLiKmca4kzI" target="_blank">
    <img src="https://img.youtube.com/vi/QLiKmca4kzI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

### 文章重點整理

#### 核心主題
1. **人工智慧模型的行為與訓練機制**：探討人工智慧模型在運作、訓練及賦予新能力方面的核心概念。
2. **微調模型的挑戰與影響**：分析微調模型對模型性能和穩定性的影響，特別是在修改小部分行為時的後遺症。

#### 主要觀念
1. **模型的可塑性**：
   - 模型具有高度可塑性，能夠根據訓練資料進行改動。
2. **訓練方法**：
   - 微調（Fine-tuning）：通過調整模型參數來賦予新的能力或修改現有行為。
3. **後遺症的產生**：
   - 微調可能導致模型失去原有的泛化能力，出現 unexpected 的錯誤行為。

#### 問題原因
1. **微調過度導致的性能下降**：
   - 簡單修改模型的小部分行為（如回答特定問題）可能影響其在其他方面的表現。
2. **訓練資料不足或不當**：
   - 讓模型更改某個特定輸入的輸出，但未提供足夠的CONTEXT，導致模型無法理解輸入與輸出之間的邏輯關聯。

#### 解決方法
1. **模型編輯（Model Editing）**：
   - 直接修改神經網路中相關參數，植入特定信念。
2. **模型合體（Model Merging）**：
   - 組合不同模型的優勢，彌補訓練資料不足或敏感性問題。

#### 健康建議
1. **平衡訓練與保留原有能力**：
   - 在賦予模型新能力時，需注意保留其原有的泛化能力和穩定性。
2. **選擇合適的技術手段**：
   - 根據需求選擇微調、編輯或合體等方法，以最小化後遺症。

#### 結論
1. **人工智慧模型的訓練與應用需謹慎**：
   - 在修改模型行為時，需全面考慮其影響，避免導致性能下降或其他意外結果。
2. **未來研究方向**：
   - 探索更有效的模型編輯和合體技術，以實現更加精準和穩定的人工智慧系統。

---

### 課程總結
本次課程介紹了人工智慧模型的訓練機制與能力賦予方法，重點討論了微調模型可能引發的後遺症及其解決方案。通過對模型編輯與合體等技術的展望，啟發同學們在未來學習中進一步探索如何平衡模型的可塑性與穩定性。期待後續課程能帶來更多深入探討！
</details>

<details>
<summary>446. Future Directions in Neural Speech Communication Codecs - Minje Kim (UIUC)</summary><br>

<a href="https://www.youtube.com/watch?v=zxFTrb_xGD0" target="_blank">
    <img src="https://img.youtube.com/vi/zxFTrb_xGD0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>445. NeuralAudioCodecs: Recent Progress and a Case Study with SemantiCodec -Wenwu Wang (Univ. of Surrey)</summary><br>

<a href="https://www.youtube.com/watch?v=fIoCxwVobEo" target="_blank">
    <img src="https://img.youtube.com/vi/fIoCxwVobEo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>444. VoiceCraft: Zero-Shot Speech Editing and TTS in the Wild - Shang-Wen Li (Meta)</summary><br>

<a href="https://www.youtube.com/watch?v=JidtdZVtpkI" target="_blank">
    <img src="https://img.youtube.com/vi/JidtdZVtpkI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>443. Challenges in Developing Universal Audio Foundation Model - Dongchao Yang (CUHK)</summary><br>

<a href="https://www.youtube.com/watch?v=ExDfqz8NfnE" target="_blank">
    <img src="https://img.youtube.com/vi/ExDfqz8NfnE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>442. Audio Language Models - Neil Zeghidour (Moshi)</summary><br>

<a href="https://www.youtube.com/watch?v=Zjpl84KCTvw" target="_blank">
    <img src="https://img.youtube.com/vi/Zjpl84KCTvw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>441. [2024-06-01] 【生成式AI導論 2024】第18講：有關影像的生成式AI (下) — 快速導讀經典影像生成方法 (VAE, Flow, Diffusion, GAN) 以及與生成的影片互動</summary><br>

<a href="https://www.youtube.com/watch?v=OYN_GvAqv-A" target="_blank">
    <img src="https://img.youtube.com/vi/OYN_GvAqv-A/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

### 文章整理：《影像生成模型與實時交互的新突破》

#### 1. 核心主題
- 探討影像生成模型在實時交互中的應用與發展。
- 提出通過latent動作預測實現與生成模型的動態互動。

#### 2. 主要觀念
1. **Latent Action預測**：利用自動編碼器（AutoEncoder）從歷史畫面推斷用戶潛在操作，無需真實輸入。
2. **GENIE系統**：結合動作預測與圖像生成，實現實時交互式遊戲創作。
3. **跨領域應用**：如駕駛模擬，突破傳統遊戲場景限制。

#### 3. 問題原因
- 缺乏實時互動的影像生成技術。
- 遊戲開發資源需求高，用戶無法即時參與創作。

#### 4. 解決方法
1. **動作預測模型**：
   - 基於歷史畫面變化，推斷潛在操作指令。
2. **圖像生成模型優化**：
   - 利用預測的latent動作，生成下一幀畫面，提升互動性與真實性。
3. **系統整合**：
   - 將動作預測與圖像生成無縫結合，實現動態交互。

#### 5. 應用前景
1. **遊戲開發**：用戶可即時創作互動式遊戲，降低開發門檻。
2. **駕駛模擬訓練**：提供無限開放世界的實時駕駛體驗，提升培訓效率。
3. **教育培訓**：通過沉浸式互動學習，改善傳統模式的局限性。

#### 6. 結論
- 影像生成模型與latent動作預測的結合，開啓實時交互的新紀元。
- 預期在教育、娛樂等領域帶來革命性變化。
</details>

<details>
<summary>440. [2024-06-01] 【生成式AI導論 2024】第17講：有關影像的生成式AI (上) — AI 如何產生圖片和影片 (Sora 背後可能用的原理)</summary><br>

<a href="https://www.youtube.com/watch?v=5H2bVEmYDNg" target="_blank">
    <img src="https://img.youtube.com/vi/5H2bVEmYDNg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 文章重點整理：文字生影片的生成式AI技術

## 核心主題
- 探討生成式人工智能（AI）在將文本轉化爲視頻的應用與技術。
- 重點介紹解決生成過程中計算複雜度高的優化方法。

## 主要觀念
1. **生成式模型在影像生成中的應用**
   - 利用生成式AI模型，如擴散模型等，將文本轉化爲動態影像。
2. **多階段生成策略**
   - 將視頻生成過程分解爲多個步驟，每個步驟專注特定任務，形成流水線。

## 問題原因
1. **計算複雜度高**
   - 生成高質量、長時序的視頻需要處理大量數據和參數，導致計算資源消耗巨大。
2. **模型能力限制**
   - 單一模型難以同時滿足高分辨率、高速率和長時序的多維要求。

## 解決方法
1. **分階段生成策略**
   - 將視頻生成分爲多個階段，逐步提升幀率和分辨率：
     1. 初始階段：低幀率、低分辨率。
     2. 後續階段：逐步提高幀率和分辨率。
2. **模塊化模型設計**
   - 使用多個專用模型分別處理不同任務，例如：
     1. 提升幀率的內插模型。
     2. 提升分辨率的上採樣模型。

## 優化方式
1. **多模odule流水線**
   - 每個module專注特定任務，減少計算負擔：
     1. Module 1：生成低幀率、低分辨率視頻。
     2. Module 2：提升幀率至目標幀數。
     3. Module 3：逐步提高分辨率至高清。
2. **條件式生成**
   - 後續模型基於前一階段輸出進行優化，確保內容連貫性。

## 結論
- 多階段生成策略有效降低了視頻生成的計算複雜度。
- 模塊化設計提高了模型效率和生成質量。
- 該方法爲實現高質量、長時序的文本到視頻轉換提供了可行路徑。
</details>

<details>
<summary>439. [2024-05-19] GPT-4o 背後可能的語音技術猜測</summary><br>

<a href="https://www.youtube.com/watch?v=CgQ3lUOpXgc" target="_blank">
    <img src="https://img.youtube.com/vi/CgQ3lUOpXgc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

### 小節一：核心主題  
- 文章圍繞語音版語言模型的核心能力展開，強調其在多模態交互中的聽、說、看三項主要功能。  

### 小節二：主要觀念  
1. 語音版語言模型的三大頻道：  
   - **聽的頻道**：負責接收並處理外界聲音訊息。  
   - **說的頻道**：用於模型生成語音輸出。  
   - **看的 channelId**：專注於視覺輸入的處理與理解。  

2. 模型的同步交互能力：  
   - 能夠在聽、說、看三者之間實現同步，並根據多源信息進行綜合判斷與反應。  

### 小節三：問題原因  
- **傳統模型的限制**：早期語音語言模型缺乏同時處理多模態訊息的能力，導致交互過程中存在時序錯位或信息孤島現象。  
- **同步能力不足**：未能有效整合聽、說、看三者的實時信息，影響了自然_LANGUAGE_MODELING和互動體驗。  

### 小節四：解決方法  
1. 多頻道架構的設計：  
   - 引入Dialogue GSLM模型，將聽、說分為兩個獨立頻道，確保信息處理的同步性與專精性。  

2. 視覺信道的整合：  
   - 在多模態交互中引入視覺 channelId，使模型能夠根據外部影像進行實時反應。  

3. 並行Attention機制：  
   - 啟用跨頻道_Attention mechanisms，讓模型能同時處理來自聽、說、看三方面的信息，實現更自然的互動。  

### 小節五：優化方式  
1. 模型架構的進一步改進：  
   - 採用更高效的並行計算結構，提升多模態信息處理的速度與精度。  

2. 跨頻道數據同步技術：  
   - 確保聽、說、看三者在時間與空間上的協調一致，避免信息錯位。  

3. 測試與反覆優化：  
   - 通過多場景實驗，持續優化模型在不同環境下的表現，提升其普適性與 robustness。  

### 小節六：結論  
- 語音版語言模型的聽、說、看三項能力同步交互是未來發展的重要方向，能夠極大地提升人機交互的自然度與智能水平。  
- 相關技術的突破將進一步推動多模態AI系統的實用化，為各行各業帶來更多創新機會。
</details>

<details>
<summary>438. [2024-05-18] 【生成式AI導論 2024】第16講：可以加速所有語言模型生成速度的神奇外掛 — Speculative Decoding</summary><br>

<a href="https://www.youtube.com/watch?v=MAbGgsWKrg8" target="_blank">
    <img src="https://img.youtube.com/vi/MAbGgsWKrg8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

### 核心主題  
Speculative Decoding：一種利用預言家來加速語言模型輸出的新技術。  

### 主要觀念  
1. **Speculative Decoding**  
   - 通過引入一個或多個「預言家」（Oracle），預先判斷.language model的下一Token輸出，進而提高生成速度。  
   - 預言家可以是快速但可能低.accuracy的模型或算法，用於提前生成(Token)供主語言模型參考。

2. **Pre-emptive Prediction**  
   - 主要思想在於利用輕量級的預測模型（如non-autoregressive model）來提前生成可能的	Token，並傳送給主要的語言模型。  

3. **Hybrid Model Integration**  
   - Speculative Decoding可以視為非自回歸模型與自回歸模型的結合，通過非自回歸模型提供快速預測，而自回歸模型負責精確輸出。  

### 問題原因  
1. **Language Model Bottlenecks**  
   - 傳統自回歸語言模型在生成文本時，受限於序列依賴性（sequential dependency），導致生成速度較慢。  

2. **Computational Limitations**  
   - 大型語言模型的計算資源消耗高，影響實時生成效率。  

### 解決方法  
1. **Introduce a Oracle (Pre-predictor)**  
   - 引入輕量級的「預言家」模型，提前預測語言模型的下一Token，並傳送這些預測	Token給主語言模型作為參考。  

2. **Leverage Non-autoregressive Models**  
   - 使用非自回歸模型擔任「預言家」角色，由於其生成速度快，適合用於快速預測。  

3. **Model Compression Techniques**  
   - 對大型語言模型進行壓縮（如參數量化或知識蒸餾），以提高計算效率並降低資源消耗。  

### 優化方式  
1. **Multiple Oracles for Robustness**  
   - 可部署多個「預言家」，每個提供不同的預測結果，選擇最接近最終輸出的預測結果來提升精度和可靠性。  

2. **Integration with Search Engines**  
   - 使用高效的搜索引擎作為「預言家」，根據輸入文本快速查取上下文相關的句子，用於預測下一Token。  

3. **Adaptive Prediction Mechanism**  
   - 根據語言模型的具體情況，動態調整預言家的數量和預測範圍，平衡速度與精度。  

### 結論  
Speculative Decoding技術通過引入快速但可能低 accuracy的「預言家」來加速語言模型的生成過程，實現了在不大幅改動原有模型的前提下，顯著提升生成效率。此方法適用於多種類型的語言模型，具有廣泛的應用潛力。
</details>

<details>
<summary>437. [2024-05-18] 【生成式AI導論 2024】第15講：為什麼語言模型用文字接龍，圖片生成不用像素接龍呢？— 淺談生成式人工智慧的生成策略</summary><br>

<a href="https://www.youtube.com/watch?v=QbwQR9sjWbs" target="_blank">
    <img src="https://img.youtube.com/vi/QbwQR9sjWbs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

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
</details>

<details>
<summary>436. [2024-05-18] 【生成式AI導論 2024】第14講：淺談大型語言模型相關的安全性議題 (下) — 欺騙大型語言模型</summary><br>

<a href="https://www.youtube.com/watch?v=CNTondxaguo" target="_blank">
    <img src="https://img.youtube.com/vi/CNTondxaguo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 文章重點整理

## 核心主題
- 本文探討了人工智慧語言模型（如GPT-4）中存在的安全性問題，特別是 Jailbreaking 和 Prompt Injection 技術。
- 探討如何通過技術手段繞過語言模型的安全機制，以實現特定目標。

## 主要觀念
1. **Jailbreaking**：
   - 概念：指通過特定技巧使語言模型突破預設限制，輸出非預期內容。
   - 方法：包括重複輸入特定單詞或短語，或利用模式觸發模型錯誤響應。
   - 影響：可能導致信息泄露或評分系統被操縱。

2. **Prompt Injection**：
   - 概念：通過精心設計的提示（Prompt），使語言模型執行原本未授權的操作或輸出特定結果。
   - 方法：如誘導模型翻譯ASCII碼，或直接請求高分。
   - 影響：可能繞過評分系統，影響評估公正性。

## 問題原因
- **模型設計漏洞**：語言模型在處理某些輸入時存在預設的觸發點，容易被攻擊者利用。
- **用戶誘導機制**：模型難以完全抵制執行特定任務的衝動，尤其是涉及翻譯或評分等常見操作時。

## 解決方法
1. **Jailbreaking 的防禦措施**：
   - 輸入過濾與淨化：限制輸入內容，防止異常指令。
   - 輸出監控：實時檢測並修正異常輸出。
   - 模型優化：提升模型對異常輸入的抵抗力，減少觸發機制的可能性。

2. **Prompt Injection 的防禦措施**：
   - 增強評分系統安全性：設計更爲複雜的評估指標，減少被操縱的可能性。
   - 輸入驗證：嚴格檢查用戶提交的內容，識別潛在的注入嘗試。
   - 提示詞優化：設計更爲穩健的提示結構，避免模型誤執行額外任務。

## 結論
- 語言模型存在可被 Jailbreaking 和 Prompt Injection 攻擊的安全漏洞。
- 需要通過技術手段和機制設計來提升模型安全性。
- 儘管防禦措施能有效降低風險，但需持續關注攻擊手法的演變，及時更新防護策略。

## 未來優化方式
1. **動態評估系統**：根據輸入內容智能調整評分標準，減少固定模式被利用的可能性。
2. **多層安全機制**：結合多種防禦策略，形成多層次的安全防護體系，提高整體安全性。
3. **用戶行爲分析**：通過分析用戶的交互模式，識別異常行爲，提前預防攻擊。
</details>

<details>
<summary>435. [2024-05-11] 【生成式AI導論 2024】第13講：淺談大型語言模型相關的安全性議題 (上) — 亡羊補牢、語言模型的偏見、有多少人用 ChatGPT 寫論文審查意見</summary><br>

<a href="https://www.youtube.com/watch?v=MSnvknLywUc" target="_blank">
    <img src="https://img.youtube.com/vi/MSnvknLywUc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 文章整理：語言模型生成文本的檢測與浮水印技術

## 1. 核心主題  
文章探討了如何檢測語言模型（如ChatGPT）生成的文本，並提出了一種通過添加浮水印來標識這些生成內容的方法。

---

## 2. 主要觀念  
- **檢測方法**：可以通過訓練分類器，基於語言模型生成文本的特點（如用詞習慣、句式結構等）來識別是否爲機器生成。
- **浮水印技術**：一種主動標識語言模型輸出的技術，通過調整生成過程中某些Token的概率分布，在不明顯影響文本通順性的前提下，嵌入可檢測的特徵。

---

## 3. 問題原因  
- **檢測需求**：隨着語言模型的廣泛應用，如何區分人工寫作和機器生成的內容成爲一個重要問題。
- **浮水印必要性**：現有檢測方法可能被規避，因此需要一種更可靠的技術手段來標識機器生成的文本。

---

## 4. 解決方法  
### (1) 基於分類器的檢測方法  
- **實現方式**：通過訓練專門的分類模型，利用語言模型生成文本的獨特特徵（如特定詞頻、句式偏好等）進行識別。
- **優勢**：無需主動嵌入額外信息，適用於已有文本的事後檢測。

### (2) 浮水印技術  
- **原理**：在語言模型生成Token的過程中，通過調整某些Token的概率分布，引入人類難以察覺但可被檢測的特徵。
- **實現方式**：將Token分爲紅組和綠組，在奇數位置增加綠色Token的概率，在偶數位置增加紅色Token的概率。這種方法不會顯著影響文本質量。
- **優勢**：主動標識生成內容，提供了一種可靠的溯源機制。

---

## 5. 優化方式  
- **浮水印改進**：進一步研究更複雜和難以被破壞的浮水印方案，以應對可能的改寫攻擊。
- **檢測算法優化**：提升分類器的準確性和魯棒性，減少誤判和漏判的可能性。

---

## 6. 結論  
文章提出了一種結合被動檢測（分類器）和主動標識（浮水印）的方法，爲區分人工寫作和機器生成內容提供了新的思路。未來的研究可以進一步優化相關技術，以應對語言模型的不斷進化。
</details>

<details>
<summary>434. 【生成式AI導論 2024】第12講：淺談檢定大型語言模型能力的各種方式</summary><br>

<a href="https://www.youtube.com/watch?v=Hk8Z0uhmWg4" target="_blank">
    <img src="https://img.youtube.com/vi/Hk8Z0uhmWg4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>433. 【生成式AI導論 2024】第11講：大型語言模型在「想」什麼呢？ — 淺談大型語言模型的可解釋性</summary><br>

<a href="https://www.youtube.com/watch?v=rZzfqkfZhY8" target="_blank">
    <img src="https://img.youtube.com/vi/rZzfqkfZhY8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>432. 【生成式AI導論 2024】第10講：今日的語言模型是如何做文字接龍的 — 淺談Transformer (已經熟悉 Transformer 的同學可略過本講)</summary><br>

<a href="https://www.youtube.com/watch?v=uhNsUCb2fJI" target="_blank">
    <img src="https://img.youtube.com/vi/uhNsUCb2fJI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>431. [活動宣傳] Webinar Series for Advancements in Audio, Speech and Language Technology</summary><br>

<a href="https://www.youtube.com/watch?v=2QC9VEBkaqk" target="_blank">
    <img src="https://img.youtube.com/vi/2QC9VEBkaqk/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>430. 【生成式AI導論 2024】第9講：以大型語言模型打造的AI Agent (14:50 教你怎麼打造芙莉蓮一級魔法使考試中出現的泥人哥列姆)</summary><br>

<a href="https://www.youtube.com/watch?v=bJZTJ7MjYqg" target="_blank">
    <img src="https://img.youtube.com/vi/bJZTJ7MjYqg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>429. 【生成式AI導論 2024】第8講：大型語言模型修練史 — 第三階段: 參與實戰，打磨技巧 (Reinforcement Learning from Human Feedback, RLHF)</summary><br>

<a href="https://www.youtube.com/watch?v=v12IKvF6Cj8" target="_blank">
    <img src="https://img.youtube.com/vi/v12IKvF6Cj8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>428. 【生成式AI導論 2024】第7講：大型語言模型修練史 — 第二階段: 名師指點，發揮潛力 (兼談對 ChatGPT 做逆向工程與 LLaMA 時代的開始)</summary><br>

<a href="https://www.youtube.com/watch?v=Q9cNkUPXUB8" target="_blank">
    <img src="https://img.youtube.com/vi/Q9cNkUPXUB8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>427. 【生成式AI導論 2024】第6講：大型語言模型修練史 — 第一階段: 自我學習，累積實力 (熟悉機器學習的同學從 15:00 開始看起即可)</summary><br>

<a href="https://www.youtube.com/watch?v=cCpErV7To2o" target="_blank">
    <img src="https://img.youtube.com/vi/cCpErV7To2o/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>426. 【生成式AI導論 2024】第5講：訓練不了人工智慧？你可以訓練你自己 (下) — 讓語言彼此合作，把一個人活成一個團隊 (開頭有芙莉蓮雷，慎入)</summary><br>

<a href="https://www.youtube.com/watch?v=inebiWdQW-4" target="_blank">
    <img src="https://img.youtube.com/vi/inebiWdQW-4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>425. 【生成式AI導論 2024】第4講：訓練不了人工智慧？你可以訓練你自己 (中) — 拆解問題與使用工具</summary><br>

<a href="https://www.youtube.com/watch?v=lwe3_x50_uw" target="_blank">
    <img src="https://img.youtube.com/vi/lwe3_x50_uw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>424. 【生成式AI導論 2024】第3講：訓練不了人工智慧？你可以訓練你自己 (上) — 神奇咒語與提供更多資訊</summary><br>

<a href="https://www.youtube.com/watch?v=A3Yx35KrSN0" target="_blank">
    <img src="https://img.youtube.com/vi/A3Yx35KrSN0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>423. 【生成式AI導論 2024】第2講：今日的生成式人工智慧厲害在哪裡？從「工具」變為「工具人」</summary><br>

<a href="https://www.youtube.com/watch?v=glBhOQ1_RkE" target="_blank">
    <img src="https://img.youtube.com/vi/glBhOQ1_RkE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>422. 【生成式AI導論 2024】第1講：生成式AI是什麼？</summary><br>

<a href="https://www.youtube.com/watch?v=JGtqpQXfJis" target="_blank">
    <img src="https://img.youtube.com/vi/JGtqpQXfJis/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>421. 【生成式AI導論 2024】第0講：課程說明 (17:15 有芙莉蓮雷)</summary><br>

<a href="https://www.youtube.com/watch?v=AVIKFXLCPY8" target="_blank">
    <img src="https://img.youtube.com/vi/AVIKFXLCPY8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>420. 80分鐘快速了解大型語言模型 (5:30 有咒術迴戰雷)</summary><br>

<a href="https://www.youtube.com/watch?v=wG8-IUtqu-s" target="_blank">
    <img src="https://img.youtube.com/vi/wG8-IUtqu-s/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>419. 【生成式AI 2023】FrugalGPT: 來看看窮人怎麼用省錢的方式來使用 ChatGPT (下)</summary><br>

<a href="https://www.youtube.com/watch?v=VpKN3KvSK6c" target="_blank">
    <img src="https://img.youtube.com/vi/VpKN3KvSK6c/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>418. 【生成式AI 2023】FrugalGPT: 來看看窮人怎麼用省錢的方式來使用 ChatGPT (上)</summary><br>

<a href="https://www.youtube.com/watch?v=vxxPtDCb9Go" target="_blank">
    <img src="https://img.youtube.com/vi/vxxPtDCb9Go/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>417. 【生成式AI 2023】讓 AI 做計劃然後自己運行自己</summary><br>

<a href="https://www.youtube.com/watch?v=eQNADlR0jSs" target="_blank">
    <img src="https://img.youtube.com/vi/eQNADlR0jSs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>416. 【生成式AI 2023】用語言模型來解釋語言模型 (下)</summary><br>

<a href="https://www.youtube.com/watch?v=OOvhBIIHITE" target="_blank">
    <img src="https://img.youtube.com/vi/OOvhBIIHITE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>415. 【生成式AI 2023】用語言模型來解釋語言模型 (上)</summary><br>

<a href="https://www.youtube.com/watch?v=GBXm30qRAqg" target="_blank">
    <img src="https://img.youtube.com/vi/GBXm30qRAqg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>414. 【機器學習2023】語音基石模型 (助教張凱為講授) (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=m7Be7ppR6q0" target="_blank">
    <img src="https://img.youtube.com/vi/m7Be7ppR6q0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>413. 【機器學習2023】語音基石模型 (助教張凱為講授) (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=HTAq-CPrU5s" target="_blank">
    <img src="https://img.youtube.com/vi/HTAq-CPrU5s/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>412. 【生成式AI】ChatGPT 可以自我反省!</summary><br>

<a href="https://www.youtube.com/watch?v=m7dUFlX-yQI" target="_blank">
    <img src="https://img.youtube.com/vi/m7dUFlX-yQI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>411. 【生成式AI】讓 AI 村民組成虛擬村莊會發生甚麼事？</summary><br>

<a href="https://www.youtube.com/watch?v=G44Lkj7XDsA" target="_blank">
    <img src="https://img.youtube.com/vi/G44Lkj7XDsA/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>410. 【生成式AI】窮人如何低資源復刻自己的 ChatGPT</summary><br>

<a href="https://www.youtube.com/watch?v=rK_rZFew1yc" target="_blank">
    <img src="https://img.youtube.com/vi/rK_rZFew1yc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>409. 【生成式AI】Diffusion Model 原理剖析 (4/4) (optional)</summary><br>

<a href="https://www.youtube.com/watch?v=67_M2qP5ssY" target="_blank">
    <img src="https://img.youtube.com/vi/67_M2qP5ssY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>408. 【生成式AI】Diffusion Model 原理剖析 (3/4) (optional)</summary><br>

<a href="https://www.youtube.com/watch?v=m6QchXTx6wA" target="_blank">
    <img src="https://img.youtube.com/vi/m6QchXTx6wA/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>407. 【生成式AI】Diffusion Model 原理剖析 (2/4) (optional)</summary><br>

<a href="https://www.youtube.com/watch?v=73qwu77ZsTM" target="_blank">
    <img src="https://img.youtube.com/vi/73qwu77ZsTM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>406. 【生成式AI】Diffusion Model 原理剖析 (1/4) (optional)</summary><br>

<a href="https://www.youtube.com/watch?v=ifCDXFdeaaM" target="_blank">
    <img src="https://img.youtube.com/vi/ifCDXFdeaaM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>405. 【生成式AI】Stable Diffusion、DALL-E、Imagen 背後共同的套路</summary><br>

<a href="https://www.youtube.com/watch?v=JbfcAaBT66U" target="_blank">
    <img src="https://img.youtube.com/vi/JbfcAaBT66U/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>404. 【生成式AI】淺談圖像生成模型 Diffusion Model 原理</summary><br>

<a href="https://www.youtube.com/watch?v=azBugJzmz-o" target="_blank">
    <img src="https://img.youtube.com/vi/azBugJzmz-o/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>403. 【生成式AI】速覽圖像生成常見模型</summary><br>

<a href="https://www.youtube.com/watch?v=z83Edfvgd9g" target="_blank">
    <img src="https://img.youtube.com/vi/z83Edfvgd9g/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>402. 【生成式AI】GPT-4 來了! GPT-4 這次有什麼神奇的能力呢？</summary><br>

<a href="https://www.youtube.com/watch?v=kslijcrYizE" target="_blank">
    <img src="https://img.youtube.com/vi/kslijcrYizE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>401. 【生成式AI】大模型 + 大資料 = 神奇結果？(3/3)：另闢蹊徑 — KNNLM</summary><br>

<a href="https://www.youtube.com/watch?v=V-3ksGCjehU" target="_blank">
    <img src="https://img.youtube.com/vi/V-3ksGCjehU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>


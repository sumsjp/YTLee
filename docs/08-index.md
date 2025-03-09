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
<summary>440. 【生成式AI導論 2024】第17講：有關影像的生成式AI (上) — AI 如何產生圖片和影片 (Sora 背後可能用的原理)</summary><br>

<a href="https://www.youtube.com/watch?v=5H2bVEmYDNg" target="_blank">
    <img src="https://img.youtube.com/vi/5H2bVEmYDNg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>439. GPT-4o 背後可能的語音技術猜測</summary><br>

<a href="https://www.youtube.com/watch?v=CgQ3lUOpXgc" target="_blank">
    <img src="https://img.youtube.com/vi/CgQ3lUOpXgc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>438. 【生成式AI導論 2024】第16講：可以加速所有語言模型生成速度的神奇外掛 — Speculative Decoding</summary><br>

<a href="https://www.youtube.com/watch?v=MAbGgsWKrg8" target="_blank">
    <img src="https://img.youtube.com/vi/MAbGgsWKrg8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>437. 【生成式AI導論 2024】第15講：為什麼語言模型用文字接龍，圖片生成不用像素接龍呢？— 淺談生成式人工智慧的生成策略</summary><br>

<a href="https://www.youtube.com/watch?v=QbwQR9sjWbs" target="_blank">
    <img src="https://img.youtube.com/vi/QbwQR9sjWbs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>436. 【生成式AI導論 2024】第14講：淺談大型語言模型相關的安全性議題 (下) — 欺騙大型語言模型</summary><br>

<a href="https://www.youtube.com/watch?v=CNTondxaguo" target="_blank">
    <img src="https://img.youtube.com/vi/CNTondxaguo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>435. 【生成式AI導論 2024】第13講：淺談大型語言模型相關的安全性議題 (上) — 亡羊補牢、語言模型的偏見、有多少人用 ChatGPT 寫論文審查意見</summary><br>

<a href="https://www.youtube.com/watch?v=MSnvknLywUc" target="_blank">
    <img src="https://img.youtube.com/vi/MSnvknLywUc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


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


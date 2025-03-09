<details>
<summary>351. [ML 2021 (English version)] Lecture 27: Domain Adaptation</summary><br>

<a href="https://www.youtube.com/watch?v=8AKqH6V9kjE" target="_blank">
    <img src="https://img.youtube.com/vi/8AKqH6V9kjE/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 27: Domain Adaptation


</details>

<details>
<summary>352. [ML 2021 (English version)] Lecture 29: Introduction of Reinforcement Learning (RL) (2/5)</summary><br>

<a href="https://www.youtube.com/watch?v=jbN0oYLtXps" target="_blank">
    <img src="https://img.youtube.com/vi/jbN0oYLtXps/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 29: Introduction of Reinforcement Learning (RL) (2/5)


</details>

<details>
<summary>353. [2021-06-05] 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (三) - Actor-Critic</summary><br>

<a href="https://www.youtube.com/watch?v=kk6DqWreLeU" target="_blank">
    <img src="https://img.youtube.com/vi/kk6DqWreLeU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (三) - Actor-Critic

# 文章整理：強化學習中的價值函數與策略優化

## 小節一：核心主題
- 強化學習（Reinforcement Learning, RL）的核心目標是通過試錯來學習 optimal 策略。
- 價值函數（Value Function）在.rl中扮演關鍵角色，用於估計某個 states 的期望累積獎勵。

## 小節二：主要觀念
1. **價值函數的定義**：
   - 儀值函數 V(S) 表示從狀態 S 出發，按照策略 π 累積獎勵的期望值。
   - Q-價值函數 Q(S, A) 表示在狀態 S 下執行行動 A 後的期望累積獎勵。

2. **策略優化的目標**：
   - 策略 π 的目標是最大化每一步的即時獎勵，最終提升整體的累積獎勵。
   - 策略可以表示為條件機率分布，描述在每個狀態下採取各個行動的概率。

3. **樣本的重要影響**：
   - 強化學習的效果高度依賴於_sampling_ 的質量。良好的樣本能有效提升學習效果，反之則可能導致訓練失敗。

## 小節三：問題原因
1. **樣本不足的限制**：
   - 在某些情況下，特定狀態轉移（如 Sa 後面接 Sb）缺乏足夠的樣本，影響模型的學習能力。
   
2. **環境隨機性的挑戰**：
   - 環境中的不確定性導致價值函數 V(S) 代表的是期望值，而非固定的結果。這增加了估計的複雜性。

3. **行動分佈的理解不足**：
   - 理解_actor_ 的行動分佈至關重要。Actor 通過.softmax函數將行動分數轉換為機率分佈，根據此分佈進行抽樣。

## 小節四：解決方法
1. **增加樣本多樣性**：
   - 利用探索策略（如 ε-greedy）或 randomness 增加不同狀態轉移的樣本數量。
   
2. **價值函數的期望估計**：
   - 面對環境隨機性，價值函數 V(S) 使用期望值來捕獲所有可能結果的平均獎勵。

3. **_actor_ 分佈的建模**：
   - 將.Actor 看作條件機率分佈，在每個狀態下根據.softmax分佈進行行動抽樣，模擬人類的策略選擇。

## 小節五：優化方式
1. **Rainbow 方法**：
   - Rainbow 是一種知名的 DQN 變體，整合了七種改進技術，提升算法的穩定性和性能。
   
2. **經驗回放機制**：
   - 使用回放記憶庫儲存歷史樣本，隨機抽取進行訓練，增強樣本多樣性並降低短期相關性影響。

3. **軟最大值技術**：
   - 在.Actor 的行動分佈建模中使用Softmax函數，將分數轉換為溫和的機率分佈，平衡探索與利用。

## 小節六：結論
- 強化學習的成功依賴於價值函數的精準估計和Actor 分佈的有效建模。
- 樣本的多樣性和環境的不確定性是影響學習效果的重要因素。
- Rainbow 等先進算法為提升.rl性能提供了有效途徑，未來研究可進一步優化這些方法。
</details>

<details>
<summary>354. [2021-06-05] 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (四) - 回饋非常罕見的時候怎麼辦？機器的望梅止渴</summary><br>

<a href="https://www.youtube.com/watch?v=73YyF1gmIus" target="_blank">
    <img src="https://img.youtube.com/vi/73YyF1gmIus/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (四) - 回饋非常罕見的時候怎麼辦？機器的望梅止渴

### 小節一：核心主題
- **Curiosity-BasedRewardShaping**  
  探討如何利用好奇心 механизみな.rl算法中，激發學習機器探索新環境的能力。

### 小節二：主要觀念
1. **獎勵塑造（RewardShaping）**  
   在原始.reward之外，加入額外的獎勵信號以引導學習過程。
2. **好奇心驅動的學習**  
   機器被設計為偏好探索新奇或未知的事物，從而主動發現環境結構。
3. **稀疏獎勵（SparseRewards）**  
   在某些任務中，正向獎勵信號出現頻率低，限制了傳統RL算法的學習效率。

### 小節三：問題原因
1. **稀疏獎勵的挑戰**  
   異常.reward sparse使得Agent難以有效學習，尤其是在複雜環境下。
2. **無意義的新奇性**  
   一些看似新奇但對任務無助的刺激（如畫面雜訊）可能幹擾 learning process。

### 小節四：解決方法
1. **Curiosity-BasedRewardShaping**  
   結合原始.reward和探索獎勵，激發Agent主動發現環境結構。
2. **有意義的新奇性檢測**  
   遴自製限新奇性的定義，確保Agent探索的目標具備實質價值。

### 小節五：優化方式
1. **CuriosityMechanism**  
   設計特定機制以量化新奇性，並將其轉換為可操作的獎勵信號。
2. **環境適應性**  
   確保新奇性檢測能有效區分有意義和無意義的新刺激。

### 小節六：結論
- **Curiosity-BasedRL的潛力**  
  通過激發好奇心，Agent能在缺乏明確.reward的情境下自發學習。
- **未來研究方向**  
  需進一步優化新奇性檢測方法，並探索其在不同環境中的應用效果。
</details>

<details>
<summary>355. [2021-06-05] 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (五) - 如何從示範中學習？逆向增強式學習 (Inverse RL)</summary><br>

<a href="https://www.youtube.com/watch?v=75rZwxKBAf0" target="_blank">
    <img src="https://img.youtube.com/vi/75rZwxKBAf0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】概述增強式學習 (Reinforcement Learning, RL) (五) - 如何從示範中學習？逆向增強式學習 (Inverse RL)

### 核心主題：.inverse Reinforcement Learning (IRL) 的應用與優化

#### 主要觀念：
1. **Inverse Reinforcement Learning (IRL)**：
   - IRL 是一種通過示範行為來學習_reward function_的技術，讓機器理解和實現人類的目標。
   - 基於模仿學習（Imitation Learning）和強化學習（Reinforcement Learning），IRL 能夠從人類的示範中提取隱含的價值判斷。

2. **核心概念**：
   - **Demonstration**: 機器通過觀察人類的示範行為來學習。
   - **Reward Function**: IRL 的目標是從示範數據中推導出_reward function_，用以指導機器的決策和行動。

3. **應用場景**：
   - 教導機械臂完成複雜任務（如擺盤子、倒東西）。
   - 通過視覺示範教導機器實現目標，無需編寫明確的控制算法。

#### 問題原因：
1. **傳統方法的限制**：
   - 基於規則的控制方法需要人工編寫詳細的行動規則，缺乏靈活性。
   - 強化學習直接在大環境中試錯效率低，且人類示範能提供更高效的教學信號。

2. **IRL 的挑戰**：
   - 機器可能完全模仿人類行為，限制了創造性和-optimal_解的實現。

#### 解決方法：
1. **IRL 的實施步驟**：
   - **收集數據**: 通過示範數據學習_reward function。
   - **學習_reward function_: 利用算法（如最大熵 IRL 或 GAIL）從示範中推導.reward_函數。
   - **強化學習優化**: 在已知.reward_函數下，進一步優化行動策略。

2. **具體技術**：
   - 使用 NIPS 和 ICML 等頂級會議的最新研究成果，提升機器理解和實現目標的能力。
   - 機器通過自我創建目標並嘗試達成，類似於人類學習和自發性探索。

#### 優化方式：
1. **超越人類示範**：
   - 在已學習到.reward_函數的基礎上，增加額外的_reward terms_（如速度、效率）。
   - 這些額外的限制條件可以激勵機器實現超人類性能。

2. **提升靈活性和創性**：
   - 避免機器完全受限於人類示範，允許其探索不同的行動策略以尋找更優的解。

#### 結論：
1. **IRL 的價值**：
   - IRL 提供了一種高效、直觀的方式來教導機器實現複雜任務。
   - 它將人類的示範行為轉化為機器可理解的形式，降低了人工編程的難度。

2. **未來發展方向**：
   - 結合額外的_reward terms_和多目標優化算法，進一步提升機器的能力。
   - 探索更高效的學習方法，使機器在示範數據基礎上實現超越人類的性能。
</details>

<details>
<summary>356. [2021-06-05] 【機器學習2021】機器終身學習 (Life Long Learning, LL) (一) - 為什麼今日的人工智慧無法成為天網？災難性遺忘(Catastrophic Forgetting)</summary><br>

<a href="https://www.youtube.com/watch?v=rWF9sg5w6Zk" target="_blank">
    <img src="https://img.youtube.com/vi/rWF9sg5w6Zk/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】機器終身學習 (Life Long Learning, LL) (一) - 為什麼今日的人工智慧無法成為天網？災難性遺忘(Catastrophic Forgetting)

### 核心主題：Life Long Learning（終身學習）的挑戰與評估方法

#### 主要觀念：
1. **終身學習的定義**：
   - 終身學習是指機器在面對一系列連續任務時，能夠逐漸適應並提高性能，而不斷更新其知識和能力。

2. **主要挑戰**：
   - **數據災氾（Data Flood）**：隨著新任務的引入，舊任務的數據逐漸被淹沒，導致模型可能遺忘或無法有效遷移已有知識。
   - **知識遷移的困難性**：新舊任務之間可能存在概念差異，機器需要有效地將已習得的知識應用到新的情境中。

3. **評估方法的核心思想**：
   - 終身學習的效果通常通過模型在完成所有任務後，對先前所有任務的性能進行綜合評估來衡量。
   - 評估方法包括向前遷移（Forward Transfer）和向後遷移（Backward Transfer），用於分析模型在新增任務後對舊任務影響的程度。

#### 問題原因：
1. **數據淹沒**：
   - 新任務的大量數據可能蓋過舊任務的數據，導致模型性能下降。
   
2. **遷移學習的局限性**：
   - 現有方法往往未能有效處理新舊任務之間的概念差異，影響遷移效果。

#### 解cision 方法：
1. **向前遷移（Forward Transfer）**：
   - 評估在未接觸到某項新任務時，模型已掌握的能力。
   - 使用指標：$RT-1, T$ 指標，計算在新增任務前後模型性能的提升。

2. **向後遷移（Backward Transfer）**：
   - 評估學習新任務後對舊任務性能的影響。
   - 使用指標：$R_{T-1, 1}$ 和 $R_1,1$，計算在新增任務前後舊任務性能的下降幅度。

3. **綜合評估方法**：
   - 將所有任務完成後的正確率平均值作為終身學習系統的整體評估指標。
   - 評估模型在完成所有任務後對早期任務的保持能力，通常會逐漸降低。

#### 優 化 方 式：
1. **提出高階遷移機制**：
   - 採用更加智能的遷移學習策略，例如使用元學習（Meta-Learning）或多層次表示學習，來提高舊任務知識的保留和新舊任務之間的遷移效果。

2. **數據平衡技術**：
   - 引入數據再加權或生成技術，平衡新舊任務的數據影響力，防止數據淹沒現象。

3. **網絡架構優化**：
   - 設計特定的神經網絡結構，如分離式憶憶儲單元，來保存和更新不同任務的知識，避免相互幹擾。

#### 結論與展望：
1. **目前挑戰**：
   - 大多數終身學習方法仍舊面臨遷移效率低、數據淹沒等問題，導致性能未能達到理想狀態。
   - 向後遷移（Backward Transfer）指標通常為負，表顯模型在新增任務後舊能力的下降。

2. **未來方向**：
   - 開發更加高效的遷移學習算法，提升新舊任務之間的知識共享和保留效果。
   - 探索新型網絡架構和數據處理技術，以應對終身學習中的多樣化挑戰。
</details>

<details>
<summary>357. [2021-06-05] 【機器學習2021】機器終身學習 (Life Long Learning, LL) (二) - 災難性遺忘(Catastrophic Forgetting)的克服之道</summary><br>

<a href="https://www.youtube.com/watch?v=Y9Jay_vxOsM" target="_blank">
    <img src="https://img.youtube.com/vi/Y9Jay_vxOsM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】機器終身學習 (Life Long Learning, LL) (二) - 災難性遺忘(Catastrophic Forgetting)的克服之道

### 研究領域：終身學習（Lifelong Learning）/ 持續學習（Continual Learning）

#### 核心概念：
- **終身學習（Lifelong Learning）**：指機器在現實環境中逐步接觸新任務，並在不遺忘舊知識的前提下，不斷提升學習能力。
- **持續學習（Continual Learning）**：強調模型在線性時間內處理非穩態數據流的能力，避免 catastrophic forgetting。

---

### 文章重點整理

#### 1. 核心主題
- 探討終身學習的三個情境及其挑戰。
- 強調模型在連續任務學習中避免知識遺忘的重要性。
- 分析不同學習策略對模型性能的影響。

#### 2. 主要觀念
- **非穩態數據流**：學習任務和數據分布隨時間變化，且新舊任務相互影響。
- **逐次任務學習**：模型需在接觸每一項新任務後，保持並提升已有能力。
- ** Curriculum Learning**：通過合理安排學習任務的順序，提高學習效率。

#### 3. 問題原因
- **Catastrophic Forgetting**：傳統深度學習方法易因更新參數而遺忘舊知識。
- **任務依賴性**：新舊任務之間的特性差異可能互相干擾。
- **模型容量限制**：固定架構難以適應不斷增加的新任務。

#### 4. 解決方法
##### (1) 知識保存技術
- **早期 freezing 技術**：鎖定關鍵網路層，防止其參數更新。
- ** elastic weight consolidation**：動態調控 synaptic intelligence，保護重要權重。
- **Progressive Neural Networks**：逐次增加新ネットワーク層，避免幹擾舊結構。

##### (2) 數據保存技術
- **生成數據方法**：利用GAN等模型生成虛擬數據，平衡新舊任務的訓練數據量。
- **經驗回放**：存儲並重複使用過去任務的數據，防止遺忘。

##### (3) 網路架構優化
- **多任務學習架構**：設計共享和專用子網絡，實現多任務協作。
- **分模塊結構**：將網路劃分為可更新和不可更新部分，平衡新舊任務需求。

#### 5. 優化方式
- ** Curriculum Learning**：按特定順序學習任務，降低 catastrophic forgetting 的風險。
- **動態模型調整**：根據新舊任務特性，動態優化模型架構和參數。
- **聯合學習策略**：結合知識保存、數據生成和網絡架構優化，提升整體性能。

#### 6. 結論
- 終身學習在實際應用中具有重要意義，需綜合考慮任務特性、模型架枸和學習策略。
- 相同順序的任務學習效果差異明顯， Curriculum Learning 可顯著提升學習效率。
- 未來研究可進一步探索更高效的知識保存方法和動態適應機制。

---

### 研究領域重要概念
1. **終身學習（Lifelong Learning）**：指機器在不斷變化的環境中，持續接觸新任務並累積知識的能力。
2. **持續學習（Continual Learning）**：強調模型在處理非穩態數據流時的實時性與有效性。
3. ** Curriculum Learning**：通過合理安排學習內容的順序，提升學習效率和效果的方法。

---

以上為文章整理之重點，各小節以條列格式清晰地闡述了核心主題、主要觀念、問題原因、解決方法、優化方式及結論。
</details>

<details>
<summary>358. [2021-06-05] 【機器學習2021】神經網路壓縮 (Network Compression) (一) - 類神經網路剪枝 (Pruning) 與大樂透假說 (Lottery Ticket Hypothesis)</summary><br>

<a href="https://www.youtube.com/watch?v=utk3EnAUh-g" target="_blank">
    <img src="https://img.youtube.com/vi/utk3EnAUh-g/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】神經網路壓縮 (Network Compression) (一) - 類神經網路剪枝 (Pruning) 與大樂透假說 (Lottery Ticket Hypothesis)

### 文章重點整理

#### 核心主題
- **網絡修剪（Network Pruning）的有效性與影響**
- **大樂透假說（Lottery Ticket Hypothesis, LTH）的討論與爭議**

#### 主要觀念
1. **大樂透假說的核心思想**：
   - 經過訓練後的大型神經網絡中，存在一些小型的子網絡（_lottery tickets_），這些子網絡在隨機初始化時即具有良好的學習能力。
   - 修剪大型網絡以保留這些優秀的子網絡，並在修剪後進行微調，可以達到與原網絡相近或甚至更佳的性能。

2. **反對大樂透假說的研究**：
   - 某些研究指出，直接訓練小型網絡（而非修剪後的網絡）在適當調整訓練參數的情況下，可以獲得 competitive 的性能。
   - 網絡修剪的效果可能受到學習率和修剪策略的影響。

#### 問題原因
1. **大樂透假說的局限性**：
   - 修剪後的網絡需要依賴從大型網絡中繼承的參數，這限制了其通用性和可解釋性。
   - 在某些情況下（如高.learning rate或結構化修剪），大樂透假說的效果並不顯著。

2. **直接訓練小型網絡的挑戰**：
   - 小型網絡在訓練初期可能表現 inferior，但通過增加訓練步數或調整超參數，可以逐步提升性能。

#### 解決方法
1. **修剪後網絡的微調**：
   - 在修剪大型網絡後，對保留的部分進行額外的微調以優化性能。

2. **直接訓練小型網絡的策略**：
   - 增加訓練數據或訓練步數。
   - 調整學習率和正則化參數以提高訓練效果。

3. **多樣化修剪策略**：
   - 採用結構化修剪（如按通道或 neurons 進行修剪），而非完全不結構化的修剪，可能獲得更好的結果。

#### 結論
1. **大樂透假說的影響**：
   - 儘管在某些條件下成立，但其普適性受到質疑。未來的研究需要進一步探討其適用範圍和限制。

2. **網絡修剪與直接訓練的平衡**：
   - 修剪技術在特定情況下有效，但直接訓練小型網絡在適當調整後也可以獲得競爭力。
   - 網絡規模的選擇應該根據具體任務和數據集來定。

3. **未來研究方向**：
   - 探討不同修剪策略對性能的影響。
   - 深入研究大樂透假說在不同架構和任務中的表現。
   - 資源受限的情況下，探索如何在不依賴大型網絡的前提下，提升小型模型的效果。

---

### 總結
文章圍繞網絡修剪的有效性展開了深入探討，既肯定了大樂透假說的貢獻，也指出了其局限性。同時，提出了直接訓練小型網絡的可能性和條件，為網絡設計提供了多樣化的選擇。未來的研究需進一步驗證不同策略在各種場景下的效果，以期找到最優的模型壓縮與訓練方法。
</details>

<details>
<summary>359. [2021-06-11] [ML 2021 (English version)] Lecture 34: Life-long Learning (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=-2r4cqDP4BY" target="_blank">
    <img src="https://img.youtube.com/vi/-2r4cqDP4BY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 34: Life-long Learning (2/2)

### 核心主題
- **_life-long learning (持續學習)**: 探討模型在連續任務學習中如何避免 catastrophic forgetting（災難性遺忘），並在不同任務之間保持良好的性能。

### 主要觀念
1. **Catastrophic Forgetting**: 模型在學習新任務時，可能會完全遺忘之前學到的知識。
2. **Incremental Learning**: 在不遺忘先前知識的情況下逐步學習新任務。
3. **Data Generation Methods**: 通過生成數據來緩解存儲真實數據的高成本問題。

### 問題原因
- **Task Dependency**: 後續任務的學習可能會影響先前任務的表現，尤其是當任務順序不合理時。
- **Resource Constraints**: 存儲和處理大量真實數據的需求較高。

### 解決方法
1. **Regularization Techniques**:
   - **Elastic Weight Consolidation (EWC)**: 通過限制關鍵參數的變化來保護重要權重。
   - **Synaptic Intelligence (SI)**: 動態調整參數更新，優先保留對先前任務重要的神經元。
2. **Data Generation Approaches**:
   - 使用生成對抗網絡（GANs）或其他生成模型創建合成數據，以減少對真實數據的依賴。
3. **Curriculum Learning**: 通過合理安排任務順序，逐步增加任務難度，優化學習效果。

### 優化方式
1. **Task Order Optimization**: 研究不同任務順序對學習效果的影響，尋找最優的學習路徑。
2. **Efficient Resource Utilization**: 利用生成數據代替存儲真實數據，降低計算和存儲成本。
3. **Generalization Across Tasks**: 通過優化模型結構或算法，提高模型在多任務間的泛化能力。

### 結論
- 持續學習是人工智能領域的重要研究方向，旨在實現類似人類的學習能力。
- 目前已有一些有效的解決方案，如正則化技術、數據生成方法和課程學習策略。
- 未來的研究應關注更複雜的持續學習場景，並探索如何在不同任務順序下優化模型性能。

### 參考文獻
- "Learning without Forgetting" (LwF)
- Incremental Classifier and Representation Learning (iCaRl)
</details>

<details>
<summary>360. [2021-06-11] [ML 2021 (English version)] Lecture 33: Life-long Learning (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=yAX8Ydfek_I" target="_blank">
    <img src="https://img.youtube.com/vi/yAX8Ydfek_I/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 33: Life-long Learning (1/2)

### 文章重點整理

#### 核心主題
- **_life-long learning (Lifelong Learning, L4)_**：探討機器學習模型在連續任務學習中保持性能的挑戰與方法。

#### 主要觀念
1. **連續任務學習的特性**：
   - 隨著新任務的加入，舊任務的表現會逐漸下降。
   - 最近學習的任務通常表現最佳，而早期任務可能被嚴重遺忘。

2. **評估方法**：
   - **前向遷移（Forward Transfer）**：衡量模型在未接觸特定任務時的學習效果。
   - **反向遷移（Backward Transfer）**：評估模型在完成所有任務後，對早期任務表現的影響。
   - **平均正確率**：學習完所有任務後，模型在所有任務上的平均性能。

3. **挑戰與問題**：
   - 模型在學習新任務時容易遺忘舊任務（ catastrophic forgetting）。
   - 如何量化遷移能力和遺忘程度是評估系統的重要課題。

#### 評估方法詳細解說
1. **平均正確率**：
   - 學習完所有任務後，測試模型在所有任務上的正確率並取平均。
   - 最常見的評估指標，反映模型整體性能。

2. **反向遷移（Backward Transfer）**：
   - 計算公式：$\text{Backward Transfer} = \sum_{t=1}^{T} (R_T,t - R_t,t)$。
   - 解釋：衡量完成所有任務後，模型對早期任務表現的提升或下降情況。
   - 通常為負值，若遷移能力為正則表示模型在新任務學習後提升了早期任務性能。

3. **前向遷移（Forward Transfer）**：
   - 計算公式：$\text{Forward Transfer} = R_{T-1,T} - R_{0,T}$。
   - 解釋：衡量模型在未接觸特定任務時的學習效果，評估模型的泛化能力。

#### 優化方式
- **平衡新舊任務學習**：通過正規化的技術（如 Elastic Weight Consolidation, EWC）來防止 catastrophic forgetting。
- **遷移學習策略**：設計modelo que mantenha o desempenho em tarefas anteriores ao aprender novas.

#### 總結
- 機器學習模型在連續任務學習中面臨遺忘問題，反向遷移和平均正確率是常見的評估指標。
- 反向遷移為負值代表模型性能下降，若能提出方法使遷移能力為正，表示模型具有強大的 life-long learning 能力。
- 未來研究可聚焦於設計更有效的防止遺忘技術，並探索如何提升遷移學習的效果。
</details>

<details>
<summary>361. [2021-06-11] [ML 2021 (English version)] Lecture 31: Introduction of Reinforcement Learning (RL) (4/5)</summary><br>

<a href="https://www.youtube.com/watch?v=pibO_5JhQ4U" target="_blank">
    <img src="https://img.youtube.com/vi/pibO_5JhQ4U/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 31: Introduction of Reinforcement Learning (RL) (4/5)

### 文章重點整理

#### 核心主題
- **.reward shaping 在強化學習中的應用**
- **基於好奇心的獎勵塑形方法**

#### 主要觀念
1. **Reward Shaping (獎勵塑形)**
   - 定義： Reward shaping 是一種通過設計和調整獎勵函數來指導AGENT learning過程的方法。
   - 段落位置：第2段

2. **Curiosity-Based Reward Shaping (基於好奇心的獎勵塑形)**
   - 定義： 基於好奇心的獎勵塑形是一種通過激發AGENT的好奇心，使其主動探索新環境和新事物的方法。
   - 段落位置： 第10段

3. **Sparse Rewards (稀疏獎勵)**
   - 說明： 稀疏獎勵是指在學習過程中獎勵信號出現的頻率很低，使得AGENT難以有效學習。
   - 段落位置： 第8段

4. **Meaningful New Things (有意義的新事物)**
   - 定義： 在基於好奇心的獎勵塑形中，有意義的新事物是指AGENT在探索過程中新接觸到的、具有實際意義的信息或環境變化。
   - 段落位置： 第10段

#### 啟發來源
- **ICML 2017 Paper on Curiosity-Based Reinforcement Learning**
  - 內容簡述： 本文提出了一種基於好奇心的強化學習方法，並通過實驗展示了該方法在Mario遊戲中的有效性。
  - 段落位置： 第9段

#### 問題原因
1. **Sparse Rewards Issue (稀疏獎勵問題)**
   - 說明： 稀疏獎勵使得AGENT難以從環境中獲得及時和有效的反饋，影響學習效率。
   - 段落位置： 第8段

2. **Noise in Exploration (探索中的噪聲問題)**
   - 說明： 在基於好奇心的獎勵塑形中，AGENT可能因環境中的噪聲而誤判新事物，從而影響有效探索。
   - 段落位置： 第13段

#### 解決方法
1. **Curiosity-Based Intrinsic Reward (基於好奇心的固有獎勵)**
   - 說明： 經過設計的固有獎勵函數用於激發AGENT的好奇心，使其更有可能探索新環境。
   - 段落位置： 第10段

2. **Filtering Meaningless Noise (過濾無意義噪聲)**
   - 說明： 在基於好奇心的獎勵塑形中，需設計機制以過濾無意義的新事物，如背景噪聲，確保AGENT能有效探索。
   - 段落位置： 第13段

3. **Pre-training and Fine-tuning (預訓練和微調)**
   - 說明： 在某些情況下，AGENT需要先在已知環境中進行預訓練，然後再在新環境中進行微調以提高學習效果。
   - 段落位置： 第12段

#### 總結
- **Reward Shaping的價值**： Reward shaping 是一種有效的強化學習技術，能夠通過設計獎勵函數引導AGENT learning方向。
- **Curiosity-Based 方法的創新性**： 基於好奇心的獎勵塑形方法成功地激發了AGENT的好奇心，使其在缺乏外部獎勵的情況下也能進行有效的探索和學習。
- **挑戰與改進**： 雖然基於好奇心的方法展示出了巨大的潛力，但還需要進一步研究如何過濾無意義的新事物，並提高其在不同環境中的泛化能力。

#### 參考文獻
1. Curiosity-Based Reinforcement Learning Paper (ICML 2017)
   - 貢獻： 提出了一種基於好奇心的強化學習方法，展示了其在遊戲環境中的有效性。
   
---

以上整理涵蓋了文章的核心主題、主要觀念、問題原因、解決方法、優化方式和結論等部分，每個主要概念均附有相應段落位置供查閱。
</details>

<details>
<summary>362. [2021-06-11] [ML 2021 (English version)] Lecture 30: Introduction of Reinforcement Learning (RL) (3/5)</summary><br>

<a href="https://www.youtube.com/watch?v=Cf-WkM-Xef0" target="_blank">
    <img src="https://img.youtube.com/vi/Cf-WkM-Xef0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 30: Introduction of Reinforcement Learning (RL) (3/5)

# 文章整理：深度強化學習中的策略.gradient descent 方法

## 核心主題
本文主要探討深度強化學習中策略.gradient descent方法的核心思想及其應用，特別是其在多個具體算法（如DQN和Rainbow DQN）中的實現與優化。

---

## 主要觀念

1. **策略.gradient descent的基本原理**  
   - 策略.gradient descent是一種通過梯度下降方法來最優化策略的方法，旨在最大化累積獎勵。
   - 通過將策略表示為神經網絡，並利用環境反饋來更新網絡參數，從而實現策略的迭代改進。

2. **與值函數方法的結合**  
   - 策略.gradient descent通常與值函數（V(s)）相結合，其中值函數表徵在某一狀態下平均累積獎勵的期望。
   - 如果策略產生的獎勵超過值函數的期望值，則表明策略表現優異；否則需進行調整。

3. **_sampling的重要性**  
   - 總體來看，強化學習的效果高度依賴於樣本的質量和多寡。良好的sampling能有效提高算法的訓練效果。

---

## 問題原因

1. **環境不確定性**  
   - 在某些情況下，後續狀態（S_b）並非總是跟隨先前列車狀態（S_a），這導致傳統方法難以有效學習。

2. **過於依賴固定序列**  
   - 若算法過度依賴固定的環境序列來訓練值函數，將限制其在多樣化環境中的適應能力。

---

## 解決方法

1. **強調sampling的關鍵作用**  
   - 確保足夠多且多樣化的樣本被收集，以提高值函數估計的準確性。  
   - 在實踐中，可通過增加 episodic 的數量或使用經驗重放（Experience Replay）技術來優化 sampling。

2. **利用期望值進行策略評估**  
   - 值函數V(s)被定義為在狀態s下平均累積獎勵的期望。即使環境存在 randomness，仍可通過.expectation的計算來指導策略的改進。

3. **.actor 為概率分佈的實現**  
   - 將.actor 看作一個概率分髮器，其輸出經過.softmax normalization後用於_sampling actions。這使得策略具有探索性與利用性的平衡。

---

## 優化方式

1. **多樣化的sampling策略**  
   - 使用經驗重放等技術來增加樣本的多樣性，從而提高算法的泛化能力。

2. **複合算法的集成**  
   - 如Rainbow DQN，通過整合七種不同的DQN變體（如Double DQN、 Dueling DQN等），顯著提升了算法的性能和穩定性。

3. **深度網絡的結構優化**  
   - 選擇適合task的網絡架構，並 tunes hyperparameters（例如學習率、批量大小等）以進一步提升訓練效果。

---

## 結論

策略.gradient descent方法為深度強化學習提供了一種有效的框架。通過結合值函數和.actor ，該方法能在不確定性和複雜性並存的環境中實現高效的學習與決策。未來的研究可圍繞更優化的sampling技術、網絡架構的設計以及多智能體協作等方面進一步展開，以應對更具挑戰性的應用場景。
</details>

<details>
<summary>363. [2021-06-11] [ML 2021 (English version)] Lecture 32: Introduction of Reinforcement Learning (RL) (5/5)</summary><br>

<a href="https://www.youtube.com/watch?v=9H3ShV57lHs" target="_blank">
    <img src="https://img.youtube.com/vi/9H3ShV57lHs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 32: Introduction of Reinforcement Learning (RL) (5/5)

### 小節歸納

#### 核心主題
- 強化學習（Reinforcement Learning, RL）在機器人控制和自動化行為中的應用。
- 使用 imitation learning 和 inverse reinforcement learning (IRL) 方法來教導機器完成特定任務。
- 探討機器能否超越人類能力的可能。

#### 主要觀念
1. **imitation learning**：通過示範行為讓機器學習並重現該行為。
2. **inverse reinforcement learning (IRL)**：從示範中推斷.reward function，使機器理解目標和獎勵結構。
3. **_reward function_**：定義任務的獎勵標準，指導機器完成特定目標。
4. **自主目標設置**：機器可以自創目標並探索實現方法。

#### 問題原因
- 傷害 imitation learning 的限制在於示範行為可能不完美或不易於重現。
- IRL 方法需要明確的.reward function，否則易受示範者偏好偏差影響。
- 傷害機器依賴人類示範，缺乏自主學習和改進能力。

#### 解決方法
1. **使用 IRL 獲取.reward function**：通過示範行為推斷.reward function，使機器理解目標。
2. **增加額外限制條件**：在已有的.reward function 中添加新條件，如速度要求，以激勵機器優化性能。
3. **自主目標設置**：允許機器自定目標並探索實現方法，提升學習能力。

#### 確優化方式
1. **改進 IRL 框架**：通過強化學習和多樣化的示範數據來提高.reward function 的準確性。
2. **結合其他算法**：將 IRL 與深度學習、圖像識別等技術結合，提升機器的綜合能力。
3. **人機協作優化**：人類提供示範和指導，機器自主探索和改進，實現最佳性能。

#### 結論
- 強化學習和 IRL 方法具有潛力教導機器完成複雜任務。
- 機器在特定條件下可以超越人類能力，但需藉助額外的.reward function 和限制條件。
- 未來研究應注重提升 IRL 的 robustness 和 generalization 能力，並探索人機協作的新模式。
</details>

<details>
<summary>364. [2021-06-11] 【機器學習2021】神經網路壓縮 (Network Compression) (二) - 從各種不同的面向來壓縮神經網路</summary><br>

<a href="https://www.youtube.com/watch?v=xrlbLPaq_Og" target="_blank">
    <img src="https://img.youtube.com/vi/xrlbLPaq_Og/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】神經網路壓縮 (Network Compression) (二) - 從各種不同的面向來壓縮神經網路

# 文章重點整理：網絡壓縮技術研究與應用

## 核心主題
- 網絡壓縮（Network Compression）旨在降低深度學習模型的計算複雜度和存儲需求，使其在資源受限的環境中更有效地運行。

## 主要觀念
1. **網絡架構設計**：通過設計高效的網絡結構來降低模型大小。
2. **知識蒸餾（Knowledge Distillation）**：利用.teacher model. 的知識來提升.student model. 的性能。
3. **網絡剪枝（Network Pruning）**：刪除網絡中冗餘的神經元或連接，以簡化模型。
4. **參數量化（Parameter Quantization）**：將模型權重表示為低精度數據，進一步壓縮模型大小。

## 問題原因
- 深度學習模型通常需要大量的計算資源和存儲空間，限制了其在移動設備等資源有限環境中的應用。
- 大規模模型的計算成本高昂，影響其實用性和可-scalability.

## 解決方法
1. **網絡架構設計**：
   - 引入更深思熟慮的網絡結構，如.MobileNet, EfficientNet. 等，以平衡性能和效率。
   - 使用分層結構或模塊化設計，提高計算效率。

2. **知識蒸餾**：
   - 利用高性能教師模型指導學生模型的訓練，使.student model. 在保持教師模型性能的前提下規模更小、效率更高。

3. **網絡剪枝**：
   - 啊倫基式剪枝：通過訓練後刪除冗餘神經元或連接。
   - 應用剪枝技術後，可配合微調進一步提升模型性能。

4. **參數量化**：
   - 對模型權重進行低精度量化（如使用8位整數），在損失少量精度的前提下大幅降低存儲需求。

## 優化方式
- 多種壓縮技術可以結合使用，以實現更高效的網絡壓縮效果。
  - 例如，在完成知識蒸餾後進一步應用網絡剪枝和參數量化。

## 結論
- 網絡壓縮技術為深度學習模型在移動設備和其他資源受限環境中的應用提供了有效的解決方案。
- 隨著研究的深入，未來將開發出更多高效的網絡壓縮方法，進一步推動人工智能技術的落地與應用。
</details>

<details>
<summary>365. 【機器學習2021】元學習 Meta Learning (一) - 元學習跟機器學習一樣也是三個步驟</summary><br>

<a href="https://www.youtube.com/watch?v=xoastiYx9JU" target="_blank">
    <img src="https://img.youtube.com/vi/xoastiYx9JU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】元學習 Meta Learning (一) - 元學習跟機器學習一樣也是三個步驟


</details>

<details>
<summary>366. 【機器學習2021】元學習 Meta Learning (二) - 萬物皆可 Meta</summary><br>

<a href="https://www.youtube.com/watch?v=Q68Eh-wm1Ts" target="_blank">
    <img src="https://img.youtube.com/vi/Q68Eh-wm1Ts/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】元學習 Meta Learning (二) - 萬物皆可 Meta


</details>

<details>
<summary>367. 【機器學習2021】課程結語 - 最後的業配並改編《為學一首示子姪》作結</summary><br>

<a href="https://www.youtube.com/watch?v=JXDjNh2qlfc" target="_blank">
    <img src="https://img.youtube.com/vi/JXDjNh2qlfc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2021】課程結語 - 最後的業配並改編《為學一首示子姪》作結


</details>

<details>
<summary>368. [2021-06-14] [ML 2021 (English version)] Lecture 35: Network Compression (1/2)</summary><br>

<a href="https://www.youtube.com/watch?v=CB0a3aBwND8" target="_blank">
    <img src="https://img.youtube.com/vi/CB0a3aBwND8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 35: Network Compression (1/2)

### 小節整理：文章重點歸納

#### 1. 核心主題
- 探討網絡剪枝（Network Pruning）的效果及其背後的理論機制。
- 比較兩種主要假設：**Lottery Hypothesis** 和 **Weight Agnostic Networks (WAN)**。

#### 2. 主要觀念
##### a. Lottery Hypothesis（ lottery hypothesis）
- 提出大網絡中存在「贏家通喫」的參數，這些參數在剪枝後的小網絡中能夠保持較好的性能。
- 剪枝過程通過借用大網絡中的隨機參數來提升小網絡的性能。

##### b. Weight Agnostic Networks (WAN)
- 表明即使網絡的所有參數都是隨機初始化或固定爲常數（如1.5），也可以在一定程度上實現良好的性能。
- 指出網絡的結構設計可能比參數本身更重要。

#### 3. 主要問題
##### a. Lottery Hypothesis 的局限性
- **Rethinking The Value Of Network Pruning** 這篇文章提出了相反的觀點，指出Lottery Hypothesis的現象可能僅在特定條件下成立。
- 實驗表明，當學習率較高時，無法觀察到Lottery Hypothesis的效果。

##### b. 剪枝後網絡訓練的挑戰
- 直接訓練小網絡（從隨機初始化開始）通常被認爲性能不如先訓練大網絡再進行剪枝的方法。
- 但實驗發現，如果給予足夠多的訓練 epochs，直接訓練的小網絡可以達到與剪枝後網絡相當甚至更好的性能。

#### 4. 解決方法
##### a. 針對 Lottery Hypothesis 的質疑
- **Rethinking The Value Of Network Pruning** 提出通過增加學習率或調整剪枝策略（如結構化剪枝）來驗證Lottery Hypothesis的普適性。
- 強調實驗條件（如學習率、訓練 epochs 等）對結果的重要影響。

##### b. 直接訓練小網絡
- 建議直接訓練小型網絡，並給予足夠的訓練.epoch數，可以避免對大網絡剪枝的依賴。
- 指出剪枝的優勢可能更多地來源於模型搜索（model search）而非簡單的參數保留。

#### 5. 結論與展望
##### a. Lottery Hypothesis 的適用性
- Lottery Hypothesis 可能在特定條件下成立，但其普適性仍需進一步研究。
- 不同的剪枝策略和訓練參數可能影響其效果。

##### b. WAN 的啟發
- 網絡性能不一定完全依賴於精細調控的參數，結構設計的重要性不容忽視。

##### c. 未來研究方向
- 探討不同學習率和訓練策略對Lottery Hypothesis的影響。
- 研究結構化剪枝（如通道剪枝）是否能更好地支撐Lottery Hypothesis。
- 深入分析直接訓練小型網絡的可行性與優勢。

#### 6. 參考文獻
- Lottery Hypothesis: ICLR 2019
- Rethinking The Value Of Network Pruning: ICLR 2019
- Weight Agnostic Networks: Arxiv （早期版本）

---

### 總結
文章主要圍繞網絡剪枝的效果展開討論，探討了Lottery Hypothesis 和 WAN 的核心觀念及其局限性。實驗結果表明，Lottery Hypothesis 的效果可能受限於特定條件（如學習率、訓練epochs等），而直接訓練小型網絡在某些情況下可以取得不俗的性能。未來的研究需要進一步驗證這些假說的普適性並探索更有效的剪枝策略。
</details>

<details>
<summary>369. [2021-06-17] [ML 2021 (English version)] Lecture 36: Network Compression (2/2)</summary><br>

<a href="https://www.youtube.com/watch?v=mGRdOGdOZ-4" target="_blank">
    <img src="https://img.youtube.com/vi/mGRdOGdOZ-4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# [ML 2021 (English version)] Lecture 36: Network Compression (2/2)

### 重點整理

#### 核心主題
本文主要探討深度學習模型的.compression技術，旨在在不顯著降低模型性能的前提下，減小模型大小並降低計算開銷，以應對計算資源有限或存儲空間受限的情境。

#### 主要觀念
1. **模型壓縮的重要性**：隨著深度學習模型規模的增大，模型參數量激增，導致硬件需求和運行成本上升。此背景下，模型壓縮技術成為關鍵。
2. **核心方法**：
    - **網絡架構搜索（ Neural Architecture Search, NAS）**：通過自動化搜索最佳網絡結構來降低模型複雜度。
    - **知識蒸餾（Knowledge Distillation）**：利用 teachers 模型的知識來訓練.student 模型，使.student 模型在保持性能的同時體積更小。
    - **網絡剪枝（Network Pruning）**：通過移除冗餘神經元或通道來精簡模型結構。
    - **參數量化（Parameter Quantization）**：降低模型參數的精度，例如使用 8 位整數代替 32 位浮點數。
3. **動態深度與寬度調控**：根據具體任務需求或環境條件自動調整網絡深度和寬度，以平衡性能與資源消耗。

#### 問題原因
1. **模型規模過大**：深度學習模型通常包含數百萬甚至十億個參數，這在移動設備等資源受限的平臺上難以部署。
2. **計算成本高昂**：大型模型需要大量的GPU/TPU資源進行訓練和推理，增加了運行成本。
3. **_deploy 障礙**：模型體積過大限制了其在邊緣計算、移動終端等場景中的應用。

#### 解決方法
1. **網絡架構搜索（NAS）**：
    - 自動化搜索最佳網絡結構， trades off between model complexity and performance.
    - 通過策略引導搜索過程，例如使用_rewards 基於性能指標。
2. **知識蒸餾**：
    - 使用大而精的教師模型訓練小而廉的學生模型。
    - 維度包括.temperature_scaling、動態	label_smoothing 等技術來提升.student 模型的學習效果。
3. **網絡剪枝**：
    - 基於梯度重要性或響應值來移除冗餘神經元或通道。
    - 可進一步配合低精度量化和修剪後重training 提升壓縮效果。
4. **參數量化**：
    - 降低模型參數的精度，如從 FP32 到.INT8，顯著減小模型大小。
    - 使用昆昆等算法來保持量化後的性能。
5. **動態深度與寬度調控**：
    - 根據輸入數據的複雜性自動調整網絡深度和.width。
    - 維度包括基於特徵相似性或梯度信號決定停止層數。

#### 優化方式
1. **多技術結合**：將上述方法有機結合，例如先修剪再量化，或在NAS中融入蒸餾策略，可獲得更好的壓縮效果。
2. **動態調控**：根據具體任務需求或環境條件自動調整網絡結構，實現.runtime 效能優化。
3. **低精度訓練與推理**：探索更低精度的訓練和推理技術，如混合精度訓練和量化感知訓練，提升量化後的模型性能。

#### 結論
深度學習模型壓縮技術為實際應用提供了重要突破。通過網絡架構搜索、知識蒸餾、剪枝、量化等多種方法的有機結合，可顯著降低模型複雜度而不犧牲性能。未來研究可在動態結構調控、低精度算法優化等方面進一步探索，以應對日益嚴峻的計算資源挑戰。
</details>

<details>
<summary>370. [2021-10-10] SUPERB: 語音上的自督導式學習模型居然十項全能？</summary><br>

<a href="https://www.youtube.com/watch?v=MpsVE60iRLM" target="_blank">
    <img src="https://img.youtube.com/vi/MpsVE60iRLM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# SUPERB: 語音上的自督導式學習模型居然十項全能？

# 文章重點整理

## 核心主題
本文圍繞語音自監督學習（Self-Supervised Learning, SSL）在多樣化語音任務中的應用展開討論，特別是通過SUPERBenchmark評估不同SSL模型的性能。文章強調了SSL模型在語音處理領域從專才向通才轉變的可能性，並提出了未來研究的方向。

## 主要觀念
1. **自監督學習的優勢**： SSL技術利用大量未標註語音數據進行預訓練，顯著提升了模型的通用性與性能。
2. **SUPERBenchmark的作用**：該benchmark涵蓋了多個語音處理任務，旨在客觀評估SSL模型的效果，並促進研究人員的合作與競爭。
3. **從專才到通才的轉變**：通過SUPERBenchmark的測試，發現多個SSL模型在10個不同語音任務上均能超越傳統方法。
4. **未來研究方向**：探討SSL模型如何學習通用表徵，並進一步優化模型結構與訓練策略。

## 問題原因
1. **傳統特徵提取方法的局限性**：如FBANK等 traditional features在面對多樣化語音任務時表現不足。
2. ** SSL模型的可解釋性與通用性**：需深入研究SSL模型如何在預訓練階段捕獲語音數據中的通用表徵。

## 解決方法
1. **引入SUPERBenchmark**：提供了一個綜合性評估平臺，用於測試不同SSL模型在多任務上的性能。
2. **加權求和策略（Weighted Sum）**：允許下遊模型動態選擇上遊模型的最佳層，提升了最終效果。
3. **.opendatadrive/SUPERB數據集**：提供公用與隱藏數據集，保障了評估的公正性與可擴展性。

## 優化方式
1. **激勵研究者參與**：通過公開排行榜吸引更多研究人員加入SSL領域的研究。
2. **促進跨學科合作**：SUPERBenchmark的工作坊與特刊為研究者提供了交流平臺，推動技術進步。
3. **持續改進模型架構**：根據Benchmark的反饋結果，不斷優化_ssl算法與模型結構。

## 結論
1. **SSL模型的通用性顯現**：多個SSL模型在SUPERBenchmark上展現出超越傳統方法的能力，成為語音處理領域的重要工具。
2. **未來研究方向明確**：需進一步探討 SSL 模型如何學習到更為通用與 robust 的表徵，並探索其在更多實際應用中的可能性。
3. **研究生態的完善**：SUPERBenchmark及其相關服務為 ssl 領域的研究提供了完善的生態支撐，促進了技術的快速發展。

---

本文通過系統性地介紹_ssl 技術在語音處理領域的最新進展與挑戰，為研究者們提供了重要的參考與啟發。
</details>

<details>
<summary>371. [2021-10-16] SUPERB: Is self-supervised learning universal in speech processing tasks? (English version)</summary><br>

<a href="https://www.youtube.com/watch?v=GTjwYzFG54E" target="_blank">
    <img src="https://img.youtube.com/vi/GTjwYzFG54E/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# SUPERB: Is self-supervised learning universal in speech processing tasks? (English version)

### 小節歸納

#### 1. 核心主題  
- 探討自監督學習（Self-Supervised Learning, SSL）在語音和音頻處理中的應用及其通用性。  
- 通過SUPERB基準測試評估不同SSL模型在多種語音任務中的性能表現。  

#### 2. 主要觀念  
- 自監督學習能夠利用大量未標註數據進行有效訓練，具有顯著的潛力。  
- 傳統的FBank特徵提取方法可能不再是最佳選擇， SSL模型在多任務上表現出更好的性能。  
- 不同SSL模型的不同層可能包含適合特定任務的信息，下遊模型應有機會選擇最優層。  

#### 3. 問題原因  
- 傳統特徵提取方法（如FBank）在某些語音任務中表現有限。  
- SSL模型的各層表示信息分布不均，固定使用最後一層可能無法充分利用其潛力。  

#### 4. 解決方法  
- **SUPERB基準測試**：建立一個統一的評估框架，涵蓋多種語音相關任務（如ASR、關鍵詞 spotting 等）。  
- **多層加權求和表示**：允許下遊模型學習選擇上遊模型中哪一層的信息最爲適合特定任務。  

#### 5. 優化方式  
- 在第二輪比賽中引入了多層加權求和機制，使下遊模型能夠自適應地選擇最優的上遊模型層。  
- 鼓勵研究者上傳自己的SSL模型到SUPERB leaderboard，以促進競爭和技術進步。  

#### 6. 結論  
- 自監督學習模型在語音任務中展現出顯著的通用性，性能優於傳統的FBank方法。  
- 多層加權求和機制能夠進一步提升模型的表現。  
- 未來的研究方向應聚焦於理解這些模型如何在預訓練階段學習到通用特徵。  

#### 7. 其他重要信息  
- 鼓勵參與SUPERB挑戰、相關研討會（如AAAI 2022自監督學習工作坊）以及IEEE JSTSP的特別專刊，以推動領域的發展。  
- 提交截止日期：  
  - SUPERB Leaderboard：持續開放，建議在10月中旬前提交。  
  - AAAI 2022工作坊：11月12日截止。  
  - IEEE JSTSP專刊：本年底截止。
</details>

<details>
<summary>372. 【機器學習2022】開學囉~ 又要週更了~</summary><br>

<a href="https://www.youtube.com/watch?v=7XZR0-4uS5s" target="_blank">
    <img src="https://img.youtube.com/vi/7XZR0-4uS5s/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2022】開學囉~ 又要週更了~


</details>

<details>
<summary>373. 【機器學習 2022】再探寶可夢、數碼寶貝分類器 — 淺談機器學習原理</summary><br>

<a href="https://www.youtube.com/watch?v=_j9MVVcvyZI" target="_blank">
    <img src="https://img.youtube.com/vi/_j9MVVcvyZI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】再探寶可夢、數碼寶貝分類器 — 淺談機器學習原理


</details>

<details>
<summary>374. 【機器學習 2022】為什麼用了驗證集 (validation set) 結果卻還是過擬合(overfitting)了呢？</summary><br>

<a href="https://www.youtube.com/watch?v=xQXh3fSvD1A" target="_blank">
    <img src="https://img.youtube.com/vi/xQXh3fSvD1A/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】為什麼用了驗證集 (validation set) 結果卻還是過擬合(overfitting)了呢？


</details>

<details>
<summary>375. 【機器學習 2022】魚與熊掌可以兼得的深度學習</summary><br>

<a href="https://www.youtube.com/watch?v=yXd2D5J0QDU" target="_blank">
    <img src="https://img.youtube.com/vi/yXd2D5J0QDU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】魚與熊掌可以兼得的深度學習


</details>

<details>
<summary>376. 【機器學習 2022】各式各樣神奇的自注意力機制 (Self-attention) 變型</summary><br>

<a href="https://www.youtube.com/watch?v=yHoAq1IT_og" target="_blank">
    <img src="https://img.youtube.com/vi/yHoAq1IT_og/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】各式各樣神奇的自注意力機制 (Self-attention) 變型


</details>

<details>
<summary>377. 【機器學習 2022】如何有效的使用自督導式模型 - Data-Efficient & Parameter-Efficient Tuning (由姜成翰助教講授)</summary><br>

<a href="https://www.youtube.com/watch?v=NzElV8jTNmw" target="_blank">
    <img src="https://img.youtube.com/vi/NzElV8jTNmw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】如何有效的使用自督導式模型 - Data-Efficient & Parameter-Efficient Tuning (由姜成翰助教講授)


</details>

<details>
<summary>378. 【機器學習 2022】語音與影像上的神奇自督導式學習 (Self-supervised Learning) 模型</summary><br>

<a href="https://www.youtube.com/watch?v=lMIN1iKYNmA" target="_blank">
    <img src="https://img.youtube.com/vi/lMIN1iKYNmA/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】語音與影像上的神奇自督導式學習 (Self-supervised Learning) 模型


</details>

<details>
<summary>379. 【機器學習2022】自然語言處理上的對抗式攻擊 (由姜成翰助教講授) - Part 1</summary><br>

<a href="https://www.youtube.com/watch?v=z-lRPFFYVJc" target="_blank">
    <img src="https://img.youtube.com/vi/z-lRPFFYVJc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2022】自然語言處理上的對抗式攻擊 (由姜成翰助教講授) - Part 1


</details>

<details>
<summary>380. 【機器學習2022】自然語言處理上的對抗式攻擊 (由姜成翰助教講授) - Part 2</summary><br>

<a href="https://www.youtube.com/watch?v=68lwXWFzCmg" target="_blank">
    <img src="https://img.youtube.com/vi/68lwXWFzCmg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2022】自然語言處理上的對抗式攻擊 (由姜成翰助教講授) - Part 2


</details>

<details>
<summary>381. 【機器學習2022】自然語言處理上的對抗式攻擊 (由姜成翰助教講授) - Part 3</summary><br>

<a href="https://www.youtube.com/watch?v=LP3q72MwE7A" target="_blank">
    <img src="https://img.youtube.com/vi/LP3q72MwE7A/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2022】自然語言處理上的對抗式攻擊 (由姜成翰助教講授) - Part 3


</details>

<details>
<summary>382. 【機器學習2022】自然語言處理上的模仿攻擊 (Imitation Attack) 以及後門攻擊 (Backdoor Attack) (由姜成翰助教講授)</summary><br>

<a href="https://www.youtube.com/watch?v=uHKXwwQ7A_s" target="_blank">
    <img src="https://img.youtube.com/vi/uHKXwwQ7A_s/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習2022】自然語言處理上的模仿攻擊 (Imitation Attack) 以及後門攻擊 (Backdoor Attack) (由姜成翰助教講授)


</details>

<details>
<summary>383. 【機器學習 2022】惡搞自督導式學習模型 BERT 的三個故事</summary><br>

<a href="https://www.youtube.com/watch?v=Pal2DbmiYpk" target="_blank">
    <img src="https://img.youtube.com/vi/Pal2DbmiYpk/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】惡搞自督導式學習模型 BERT 的三個故事


</details>

<details>
<summary>384. 【機器學習 2022】各種奇葩的元學習 (Meta Learning) 用法</summary><br>

<a href="https://www.youtube.com/watch?v=QNfymMRUg3M" target="_blank">
    <img src="https://img.youtube.com/vi/QNfymMRUg3M/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【機器學習 2022】各種奇葩的元學習 (Meta Learning) 用法


</details>

<details>
<summary>385. AlphaTensor: 用增強式學習 (Reinforcement Learning) 找出更有效率的矩陣相乘演算法 (線性代數 2022 課程補充)</summary><br>

<a href="https://www.youtube.com/watch?v=KPcA8QCTm5U" target="_blank">
    <img src="https://img.youtube.com/vi/KPcA8QCTm5U/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# AlphaTensor: 用增強式學習 (Reinforcement Learning) 找出更有效率的矩陣相乘演算法 (線性代數 2022 課程補充)


</details>

<details>
<summary>386. Meta 語音對語音翻譯技術背後的黑科技 (在繪圖 AI 中也有用上喔!)</summary><br>

<a href="https://www.youtube.com/watch?v=sWz4e-DM4JU" target="_blank">
    <img src="https://img.youtube.com/vi/sWz4e-DM4JU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# Meta 語音對語音翻譯技術背後的黑科技 (在繪圖 AI 中也有用上喔!)


</details>

<details>
<summary>387. ChatGPT (可能)是怎麼煉成的 - GPT 社會化的過程</summary><br>

<a href="https://www.youtube.com/watch?v=e0aKI2GGZNg" target="_blank">
    <img src="https://img.youtube.com/vi/e0aKI2GGZNg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# ChatGPT (可能)是怎麼煉成的 - GPT 社會化的過程


</details>

<details>
<summary>388. 【生成式AI】ChatGPT 原理剖析 (1/3) — 對 ChatGPT 的常見誤解</summary><br>

<a href="https://www.youtube.com/watch?v=yiY4nPOzJEg" target="_blank">
    <img src="https://img.youtube.com/vi/yiY4nPOzJEg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】ChatGPT 原理剖析 (1/3) — 對 ChatGPT 的常見誤解


</details>

<details>
<summary>389. 【生成式AI】ChatGPT 原理剖析 (2/3) — 預訓練 (Pre-train)</summary><br>

<a href="https://www.youtube.com/watch?v=1ah7Qsri_c8" target="_blank">
    <img src="https://img.youtube.com/vi/1ah7Qsri_c8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】ChatGPT 原理剖析 (2/3) — 預訓練 (Pre-train)


</details>

<details>
<summary>390. [2023-02-24] 【生成式AI】ChatGPT 原理剖析 (3/3) — ChatGPT 所帶來的研究問題</summary><br>

<a href="https://www.youtube.com/watch?v=UsaZhQ9bY2k" target="_blank">
    <img src="https://img.youtube.com/vi/UsaZhQ9bY2k/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】ChatGPT 原理剖析 (3/3) — ChatGPT 所帶來的研究問題

### 核心主題：人工智能（AI）系統的倫理與技術挑戰

#### 1. 主要問題領域：
- **模型調整與需求表達**：如何確保AI系統準確理解和響應用戶需求。
- **錯誤修正機制**：解決AI生成內容中的錯誤問題的方法。
- **AI生成物檢測**：識別由AI生成的內容的技術手段。
- **隱私保護與數據泄露風險**：防止AI系統無意中泄露敏感信息的策略。

#### 2. 倫理與技術挑戰分析：
- **隱私泄露問題**：AI模型可能通過間接詢問暴露個人機密信息，如地址和聯繫方式。
- **可解釋性與透明度不足**：用戶難以理解AI決策過程，影響信任。
- **數據濫用風險**：AI系統可能意外訪問或存儲不應接觸的信息。

#### 3. 解決方案與技術對策：
- **需求表達優化**：使用明確的自然語言處理方法提高指令準確性。
- **錯誤修正技術**：開發自動校正算法和用戶反饋機制來糾正生成內容中的錯誤。
- **AI生成檢測工具**：利用特徵分析和機器學習模型識別AI生成文本。
- **隱私保護措施**：實施數據脫敏、訪問限制和遺忘機制，如「Machine Unlearning」。

#### 4. 結論與未來展望：
- **提升整體水平潛力**：AI系統能幫助人類達到更高效率和創造力，成爲輔助工具。
- **倫理框架的重要性**：需建立明確的倫理規範和技術標準來指導AI系統的開發與應用。

### 主要觀點總結：

1. **需求表達優化**：
   - **Definition of Clear Requirements**: 明確界定用戶需求，提升指令準確性。
   
2. **錯誤修正技術**：
   - **Error Correction Mechanisms**: 通過自動校正和反饋系統解決AI生成內容的問題。
   
3. **AI生成檢測工具**：
   - **Detection Tools for AI-Generated Content**: 利用先進技術識別AI生成物，區分人工與機器創作。

4. **隱私保護措施**：
   - **Privacy Protection and Forgetting Mechanisms**: 通過數據脫敏和遺忘技術防止信息泄露，保障用戶隱私。

### 結論：
文章探討了在AI系統廣泛應用背景下所面臨的核心挑戰，包括需求表達、錯誤修正、生成內容識別和隱私保護。提出的解決方案和技術手段爲應對這些挑戰提供了方向，強調了倫理規範和技術標準的重要性。未來的研究應繼續關注如何提升AI系統的透明度與可解釋性，確保其安全可靠地服務於人類社會。
</details>

<details>
<summary>391. 【生成式AI】用 ChatGPT 和 Midjourney 來玩文字冒險遊戲</summary><br>

<a href="https://www.youtube.com/watch?v=A-6c584jxX8" target="_blank">
    <img src="https://img.youtube.com/vi/A-6c584jxX8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】用 ChatGPT 和 Midjourney 來玩文字冒險遊戲


</details>

<details>
<summary>392. 【生成式AI】快速了解機器學習基本原理 (1/2) (已經略懂機器學習的同學可以跳過這段)</summary><br>

<a href="https://www.youtube.com/watch?v=phQK8xZpgoU" target="_blank">
    <img src="https://img.youtube.com/vi/phQK8xZpgoU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】快速了解機器學習基本原理 (1/2) (已經略懂機器學習的同學可以跳過這段)


</details>

<details>
<summary>393. 【生成式AI】快速了解機器學習基本原理 (2/2) (已經略懂機器學習的同學可以跳過這段)</summary><br>

<a href="https://www.youtube.com/watch?v=XLyPFnephpY" target="_blank">
    <img src="https://img.youtube.com/vi/XLyPFnephpY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】快速了解機器學習基本原理 (2/2) (已經略懂機器學習的同學可以跳過這段)


</details>

<details>
<summary>394. [2023-03-03] 【生成式AI】生成式學習的兩種策略：要各個擊破，還是要一次到位</summary><br>

<a href="https://www.youtube.com/watch?v=AihBniegMKg" target="_blank">
    <img src="https://img.youtube.com/vi/AihBniegMKg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】生成式學習的兩種策略：要各個擊破，還是要一次到位

# 文章整理：生成策略在文本和影像生成中的應用

## 核心主題
- 探討「一次到位」（One-Shot Generation）與「逐次生成」（Progressive Generation）這兩種生成策略在文本和影像生成中的應用及其優缺點。

## 主要觀念
1. **一次到位生成**：
   - 特性：直接生成最終結果。
   - 優點：速度快。
   - 缺點：可能缺乏清晰度和方向感，導致輸出模糊或不準確。

2. **逐次生成（各個擊破）**：
   - 特性：逐步細化生成過程，先決定大方向再完善細節。
   - 優點：結果更清晰、準確，尤其適用於複雜任務如語音合成和圖像生成。
   - 缺點：速度較慢。

## 問題原因
- **一次到位生成的問題**：
  - 由於模型在生成過程中無法有效選擇單一策略，導致輸出模糊或混合多個可能的解。
- **逐次生成的問題**：
  - 需多次迭代，計算量大，耗時較長。

## 解決方法
1. **結合兩種生成策略**：
   - 在語音合成中，先用逐次生成確定大方向（如每秒100個向量），再用一次到位生成高頻率聲音信號。
   
2. **Diffusion Model的應用**：
   - 將「一次到位」改為多次逐步細化的過程，通過逐步去噪提高圖像清晰度。

## 優化方式
- **分階段生成**：
  - 先用逐次生成確定大方向，再用一次到位完成細節。
  
- **Diffusion Model的改進**：
  - 多次迭代去噪，提升生成質量。

## 結論
- 不同生成任務需選擇適合的策略：
  - 文本生成：一次到位可能足夠。
  - 影像和語音生成：結合逐次生成與一次到位可得更優結果。
- Diffusion Model通過多次逐步細化，顯著提升了圖像生成質量，成爲當前先進的生成模型之一。

---

此整理框架清晰地展示了文章的核心內容及其邏輯關係，便於理解和進一步研究。
</details>

<details>
<summary>395. 【生成式AI】能夠使用工具的AI：New Bing, WebGPT, Toolformer</summary><br>

<a href="https://www.youtube.com/watch?v=ZID220t_MpI" target="_blank">
    <img src="https://img.youtube.com/vi/ZID220t_MpI/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】能夠使用工具的AI：New Bing, WebGPT, Toolformer


</details>

<details>
<summary>396. [2023-03-10] 【生成式AI】Finetuning vs. Prompting：對於大型語言模型的不同期待所衍生的兩類使用方式 (1/3)</summary><br>

<a href="https://www.youtube.com/watch?v=F58vJcGgjt0" target="_blank">
    <img src="https://img.youtube.com/vi/F58vJcGgjt0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】Finetuning vs. Prompting：對於大型語言模型的不同期待所衍生的兩類使用方式 (1/3)

# 文章重點整理

## 核心主題
本文圍繞如何通過插入適配器（Adapter）技術來提升大型語言模型（如GPT-3）的多任務處理能力展開探討，強調了在不顯著增加計算和存儲負擔的情況下，實現高效微調的重要性。

## 主要觀念
1. **大型語言模型的局限性**：當前主流的大語言模型（如GPT-3）參數量巨大，直接微調整個模型來完成多個任務在計算資源和存儲空間上存在顯著限制。
2. **適配器技術的作用**：通過插入輕量級的適配器模塊，可以在不修改原始模型參數的情況下，實現針對不同任務的高效微調。

## 問題原因
1. **多任務處理的計算成本高**：直接微調大型模型以支持多個任務需要存儲和運行多個版本的大模型，這在計算資源上是不可持續的。
2. **模型更新的影響範圍大**：傳統微調方法會修改整個模型的所有參數，導致模型性能受到全局性影響。

## 解決方法
1. **適配器插入技術**：
   - 在原始模型的不同位置（如注意力層或前饋網絡）插入輕量級的適配器模塊。
   - 這些適配器通常只包含少量新增參數，可以在保持原始模型結構完整性的前提下，實現針對特定任務的微調。

2. **高效微調策略**：
   - 只對適配器參數進行微調，而保留原始大模型的參數不變。
   - 這種方法顯著降低了計算和存儲成本，使得多任務處理變得更加可行。

## 優化方式
1. **適配器設計的靈活性**：有多種適配器插入方式可供選擇，如：
   - **BitFit**：只微調神經元偏置項。
   - **Houlsby Adapter**：在前饋網絡後增加一層新的前(feed-forward)網絡。
   - **Adapter Bias**：對前饋輸出進行平移操作。
   - **Prefix Tuning**：修改注意力機制。
   - **LoRA（Low-Rank Adaptation）**：針對注意力層的低秩適配器。

2. **根據任務特性選擇適配器位置**：不同的任務可能需要將適配器插入到模型的不同位置，以獲得最佳性能。例如：
   - LoRA在自然語言處理任務中表現優異。
   - 但LoRA在語音相關任務中的效果較差，需根據具體應用場景進行選擇。

## 結論
適配器技術為大規模多任務學習提供了一種高效且可持續的解決方案。通過插入輕量級的適配器模塊，可以在不顯著增加計算和存儲負擔的前提下，實現針對不同任務的有效微調，極大地提升了模型的實用價值。

---

# 問題清單
1. **適配器技術在現實應用中是否存在性能瓶頸？**  
   - 需要進一步研究不同類型的適配器在實際場景中的性能表現及其影響因素。

2. **如何系統化地選擇適合特定任務的適配器位置和結構？**  
   - 探索基於任務特性自動選擇最佳適配器插入位置的方法。

3. **適配器技術能否進一步降低計算資源消耗？**  
   - 研究更高效的適配器設計，以進一步降低模型微調的計算成本。

4. **多適配器並行處理是否會影響模型性能？**  
   - 探索在大型語言模型中插入多個適配器的可能性及其對模型性能的影響。

5. **適配器技術能否拓展到其他模態（如圖像或語音）？**  
   - 研究適配器技術在跨模態應用中的可行性與效果。
</details>

<details>
<summary>397. [2023-03-10] 【生成式AI】Finetuning vs. Prompting：對於大型語言模型的不同期待所衍生的兩類使用方式 (2/3)</summary><br>

<a href="https://www.youtube.com/watch?v=aZ_jXZvxyVg" target="_blank">
    <img src="https://img.youtube.com/vi/aZ_jXZvxyVg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】Finetuning vs. Prompting：對於大型語言模型的不同期待所衍生的兩類使用方式 (2/3)

### 小節分類整理

#### 1. 核心主題
- 探討大型語言模型（LLM）通過指令調適（instruction tuning）實現理解和執行複雜自然語言處理任務的能力。
- 重點分析現有方法如In-context Learning和Few-shot Learning的局限性，以及Instruction Tuning在提升模型泛化能力方面的優勢。

#### 2. 主要觀念
1. **In-context Learning**：通過提供少量示例或上下文讓模型直接理解和執行指令。然而，這種方法嚴重依賴於高質量的示例，並且在面對未見過的新指令時效果有限。
2. **Instruction Tuning**：預先訓練模型理解並響應各種人類指令，使其能夠在沒有額外示例的情況下處理新任務。

#### 3. 問題原因
- 原有的In-context Learning方法依賴於高質量的示例數據，獲取這些數據往往需要大量的人力和時間。
- 模型在面對未見過的新指令時，缺乏足夠的泛化能力，導致性能下降。

#### 4. 解決方法
1. **Instruction Tuning**：
   - 收集並整理多種自然語言處理任務的數據集。
   - 將這些任務轉化爲人類可理解的指令形式，並進行模型訓練。
   - 通過大量多樣化的人類指令訓練模型，使其能夠理解並執行各種任務。

#### 5. 優化方式
1. **數據收集與整理**：
   - 收集廣泛的自然語言處理任務數據集，涵蓋翻譯、摘要、問答等多種類型。
2. **指令轉換**：
   - 將每個NLP任務轉化爲多個不同的指令描述方式，提升模型的適應性。
3. **模型訓練策略**：
   - 使用多樣化的人類指令進行監督訓練，確保模型理解不同表達方式下的同一任務。

#### 6. 結論
- Instruction Tuning是一種有效的提升LLM理解和執行複雜自然語言處理任務能力的方法。
- 通過這種方式，模型能夠在未見過的新指令下表現出色，展現出良好的泛化能力。
</details>

<details>
<summary>398. 【生成式AI】Finetuning vs. Prompting：對於大型語言模型的不同期待所衍生的兩類使用方式 (3/3)</summary><br>

<a href="https://www.youtube.com/watch?v=HnzDaEiN_eg" target="_blank">
    <img src="https://img.youtube.com/vi/HnzDaEiN_eg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】Finetuning vs. Prompting：對於大型語言模型的不同期待所衍生的兩類使用方式 (3/3)


</details>

<details>
<summary>399. [2023-03-17] 【生成式AI】大模型 + 大資料 = 神奇結果？(1/3)：大模型的頓悟時刻</summary><br>

<a href="https://www.youtube.com/watch?v=SaZTJJNOCOY" target="_blank">
    <img src="https://img.youtube.com/vi/SaZTJJNOCOY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】大模型 + 大資料 = 神奇結果？(1/3)：大模型的頓悟時刻

### 文章重點整理

#### 核心主題
1. 大模型在特定任務中的表現優於中小模型。
2. 中小型模型在某些任務中可能表現不佳，甚至劣於隨機猜測。
3. 模型規模與性能之間的複雜關係。

#### 主要觀念
1. **規模效應**：大型模型在計算期望值等複雜任務中表現更優。
2. **陷阱任務（Distractor Task）**：某些任務設計包含誤導因素，導致部分模型失敗。
3. **一知半解的風險**：中小型模型可能因有限的理解能力而做出錯誤判斷。

#### 問題原因
1. 中小型模型缺乏足夠的參數容量，無法處理複雜的上下文信息。
2. 一些任務需要重新定義基本概念（如π=10），中小型模型難以適應。
3. 模型在推理過程中未能正確計算期望值或忽視了潛在的陷阱。

#### 解決方法
1. **增加模型規模**：使用更大的參數量以提升模型的理解和處理能力。
2. **任務設計優化**：明確任務要求，減少誤導因素。
3. **混合專家模型（Mixture-of-Expert）**：通過並行計算提高效率，同時降低資源消耗。

#### 優化方式
1. 使用混合專家模型結構，在推理時僅調用部分模組以節省資源。
2. 重新定義模型架構，如Switch Transformer，以適應超大規模參數。
3. 在訓練過程中逐步增加任務的複雜度，提升模型的適應能力。

#### 結論
1. 模型規模與性能呈非線性關係，存在最佳規模點。
2. 超大規模模型在特定任務中表現更優，但需考慮計算資源限制。
3. 未來研究應關注如何平衡模型規模與效率，優化模型設計。
</details>

<details>
<summary>400. 【生成式AI】大模型 + 大資料 = 神奇結果？(2/3)：到底要多少資料才夠</summary><br>

<a href="https://www.youtube.com/watch?v=qycxA-xX_OY" target="_blank">
    <img src="https://img.youtube.com/vi/qycxA-xX_OY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 【生成式AI】大模型 + 大資料 = 神奇結果？(2/3)：到底要多少資料才夠


</details>


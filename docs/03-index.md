<details>
<summary>151. [2019-03-07] Anomaly Detection (5/7)</summary><br>

<a href="https://www.youtube.com/watch?v=Fh1xFBktRLQ" target="_blank">
    <img src="https://img.youtube.com/vi/Fh1xFBktRLQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

### 小節一：核心主題  
- 文章探討了在多人線上遊戲中，玩家行為分異（尤其是「小白」或破壞性玩家）的分析與識別方法。  
- 主要焦點放在如何通過玩家行為數據來區分正常玩家與異常玩家。  

### 小節二：主要觀念  
1. **遊戲操作機制**  
   - 遊戲中存在兩種主要狀態：無政府狀態（chaos mode）和民主狀態（democracy mode）。  
   - 無政府狀態下，玩家的行動不受他人影響；民主狀態下，每20秒由多數投票決定角色行為。  

2. **玩家行爲特徵**  
   - 正常玩家通常在無政府狀態下發言，且很少說垃圾話。  
   - 異常玩家（如小白）則可能在民主狀態下積極發言，以影響投票結果。  

3. **數據分析維度**  
   - 使用二維向量描述玩家行為：一維為「說垃圾話的機率」，另一維為「無政府狀態下發言的比例」。  

### 小節三：問題原因  
- 遊戲中存在大量異常玩家擾亂遊戲秩序，影響其他玩家體驗。  
- 無有效的量化方法來區分正常與異常玩家，導致難以實施針對性管理策略。  

### 小節四：解決方法  
1. **數據收集與 visualization**  
   - 收集並整理所有玩家的行為數據，繪製二維平面上的分布圖。  

2. **機率模型建模**  
   - 建立機率模型，計算每個玩家在各個維度上的機率分數。  
   - 通過機率分數量化玩家的正常程度。  

3. **行為模式識別**  
   - 根據機率分數，識別出異常玩家的行為模式。  

### 小節五：優化方式  
1. **提升數據分析精度**  
   - 增加更多維度（如發言頻率、行動一致性等）來進一步精細化玩家行為分析。  

2. **動態監控系統**  
   - 實現即時監控和動態調整，根據實時數據更新玩家分數。  

3. **用戶反饋機制**  
   - 引入玩家反饋，用以校正和優化模型的判斷準則。  

### 小節六：結論  
- 通過量化分析玩家行為數據，可以有效區分正常玩家與異常玩家。  
- 無政府狀態下發言比例高且垃圾話機率低的玩家更可能是正常玩家；相反，垃圾話機率高或在民主狀態下積極發言的玩家更可能是異常玩家。  
- 此方法為遊戲管理者提供了客觀、可操作的手段，用以改善遊戲操作體驗和秩序管理。
</details>

<details>
<summary>152. [2019-03-07] Anomaly Detection (6/7)</summary><br>

<a href="https://www.youtube.com/watch?v=LmFWzmn2rFY" target="_blank">
    <img src="https://img.youtube.com/vi/LmFWzmn2rFY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

### 小節一：核心主題  
- 文章圍繞著異常偵測的核心思想展開討論，強調利用概率密度函數來建模數據分布，進而識別異常樣本。

### 小節二：主要觀念  
1. **生成式模型**：文章提出使用 générative models（生成式模型）來建模數據的分布，特別是高斯分佈。
2. **概率密度函數**：通過計算每個樣本的概率密度值，來判斷其是否為異常。
3. **訓練資料的平均值和協方差矩陣**：提出利用訓練資料的平均值（μ*）和協方差矩陣（Σ*）來建模數據分布。

### 小節三：問題原因  
1. **數據分佈的假設限制**：文章強調了使用高斯分佈作為假設的局限性，指出若實際數據並非高斯分佈，則可能影響模型性能。
2. **簡單模型的不足**：基於均值和協方差的模型在面對複雜數據分佈時，缺乏 flexibility 和 expressive power。

### 小節四：解決方法  
1. **直接計算均值和協方差矩陣**：提出利用訓練資料的平均值和平均外積來計算 μ* 和 Σ*。
2. **異常偵測門檻設置**：通過development set設定門檻 λ，將數據分為正常和異常兩類。

### 小節五：優化方式  
1. **模型自由度提升**：未來可以使用更複雜的模型（如深度學習中的生成式網絡）來更好地捕捉數據特徵。
2. **數據轉換技術**：通過數據轉換技術，將非高斯分佈數據轉為接近高斯分佈，以提高模型性能。

### 小節六：結論  
1. **簡單模型的有效性**：基於均值和協方差矩陣的高斯分佈模型在某些情況下能夠有效實現異常偵測。
2. **方法局限性**：此方法對數據分佈假設有嚴苛要求，未來可考慮更 flexible 的模型來提升性能。
3. **實際應用價值**：此方法提供了一種直觀且 computationally efficient 的方式，在特定場景下具有實用價值。
</details>

<details>
<summary>153. [2019-03-07] Anomaly Detection (7/7)</summary><br>

<a href="https://www.youtube.com/watch?v=6W8FqUGYyDo" target="_blank">
    <img src="https://img.youtube.com/vi/6W8FqUGYyDo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>

# 文章整理：異常偵測的機器學習方法

## 小節一：核心主題
- 探討如何利用機器學習技術進行玩家行為的異常偵測。
- 強調特徵選擇和模型訓練在異常偵測中的重要性。

## 小節二：主要觀念
1. **特徵選擇**：
   - 選擇與玩家行為相關的所有可能特徵，例如按鍵比例、行為一致性等。
2. **模型介紹**：
   - 使用高斯分佈（Gaussian Distribution）進行生成式模型（Generative Model）訓練。
   - 提及深度學習方法如自編碼器（Auto-encoder）和傳統機器學習技術如One-Class SVM和孤立森林（Isolated Forest）。

## 小節三：問題原因
- 異常偵測的挑戰在於如何有效區分正常行為與異常行為。
- 傳統方法可能無法完全捕獲複雜的玩家行為模式。

## 小節四：解決方法
1. **生成式模型**：
   - 利用高斯分佈訓練生成模型，計算玩家行為的概率密度（likelihood）來判定其正常性。
2. **自編碼器（Auto-encoder）**：
   - 通過編碼器和解碼器的訓練，將輸入數據映射到低維空間並重建原始數據。
   - 根據還原度評估數據的異常程度。
3. **傳統機器學習方法**：
   - 使用One-Class SVM和孤立森林等算法，只需正常數據即可訓練模型來識別異常數據。

## 小節五：優化方式
- 增加更多相關特徵以提高模型的準確性。
- 結合多種方法（如生成式模型和自編碼器）進行ensemble learning，提升異常偵測的效果。

## 小節六：結論
- 機器學習技術可以有效地應用於玩家行為的異常偵測。
- 高斯分佈、自編碼器、One-Class SVM和孤立森林等方法各有優缺點，可根據具體需求選擇合適的模型。
- 異常偵測是個不斷優化的過程，需結合數據特性進行模型調整。

---

# 全文總結
本文探討了利用機器學習技術進行玩家行為異常偵測的方法，強調了特徵選擇和模型訓練的重要性。通過介紹高斯分佈、自編碼器、One-Class SVM和孤立森林等多種算法，展示了如何有效區分正常行為與異常行為。文章最後指出，異常偵測是一項需要不斷優化的技術，需根據具體需求選用合適的模型並結合數據特性進行調整。
</details>

<details>
<summary>154. Attack ML Models (1/8)</summary><br>

<a href="https://www.youtube.com/watch?v=NI6yb0WgMBM" target="_blank">
    <img src="https://img.youtube.com/vi/NI6yb0WgMBM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>155. Attack ML Models (2/8)</summary><br>

<a href="https://www.youtube.com/watch?v=zOdg05BwE7I" target="_blank">
    <img src="https://img.youtube.com/vi/zOdg05BwE7I/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>156. Attack ML Models (3/8)</summary><br>

<a href="https://www.youtube.com/watch?v=F9N5zF7N0qY" target="_blank">
    <img src="https://img.youtube.com/vi/F9N5zF7N0qY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>157. Attack ML Models (4/8)</summary><br>

<a href="https://www.youtube.com/watch?v=qjnMoWmn1FQ" target="_blank">
    <img src="https://img.youtube.com/vi/qjnMoWmn1FQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>158. Attack ML Models (5/8)</summary><br>

<a href="https://www.youtube.com/watch?v=2mgLPZJOHNk" target="_blank">
    <img src="https://img.youtube.com/vi/2mgLPZJOHNk/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>159. Attack ML Models (6/8)</summary><br>

<a href="https://www.youtube.com/watch?v=z2nmPDLEXI0" target="_blank">
    <img src="https://img.youtube.com/vi/z2nmPDLEXI0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>160. Attack ML Models (7/8)</summary><br>

<a href="https://www.youtube.com/watch?v=KH48zq2RfBA" target="_blank">
    <img src="https://img.youtube.com/vi/KH48zq2RfBA/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>161. Attack ML Models (8/8)</summary><br>

<a href="https://www.youtube.com/watch?v=ah_Ttx6cIVU" target="_blank">
    <img src="https://img.youtube.com/vi/ah_Ttx6cIVU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>162. Explainable ML (1/8)</summary><br>

<a href="https://www.youtube.com/watch?v=lnjrn3bF9lA" target="_blank">
    <img src="https://img.youtube.com/vi/lnjrn3bF9lA/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>163. Explainable ML (2/8)</summary><br>

<a href="https://www.youtube.com/watch?v=pNpk6DPYUh8" target="_blank">
    <img src="https://img.youtube.com/vi/pNpk6DPYUh8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>164. Explainable ML (3/8)</summary><br>

<a href="https://www.youtube.com/watch?v=K6TpPWLc52c" target="_blank">
    <img src="https://img.youtube.com/vi/K6TpPWLc52c/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>165. Explainable ML (4/8)</summary><br>

<a href="https://www.youtube.com/watch?v=yORbWn7UsBs" target="_blank">
    <img src="https://img.youtube.com/vi/yORbWn7UsBs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>166. Explainable ML (5/8)</summary><br>

<a href="https://www.youtube.com/watch?v=1xnhQbAV1m0" target="_blank">
    <img src="https://img.youtube.com/vi/1xnhQbAV1m0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>167. Explainable ML (8/8)</summary><br>

<a href="https://www.youtube.com/watch?v=gotiBlOu18I" target="_blank">
    <img src="https://img.youtube.com/vi/gotiBlOu18I/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>168. Explainable ML (7/8)</summary><br>

<a href="https://www.youtube.com/watch?v=OjqIVSwly4k" target="_blank">
    <img src="https://img.youtube.com/vi/OjqIVSwly4k/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>169. Explainable ML (6/8)</summary><br>

<a href="https://www.youtube.com/watch?v=K1mWgthGS-A" target="_blank">
    <img src="https://img.youtube.com/vi/K1mWgthGS-A/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>170. Unsupervised Syntactic Parsing (ft. 莊永松同學)</summary><br>

<a href="https://www.youtube.com/watch?v=YIuBHB9Ejok" target="_blank">
    <img src="https://img.youtube.com/vi/YIuBHB9Ejok/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>171. Life Long Learning (1/7)</summary><br>

<a href="https://www.youtube.com/watch?v=7qT5P9KJnWo" target="_blank">
    <img src="https://img.youtube.com/vi/7qT5P9KJnWo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>172. Life Long Learning (7/7)</summary><br>

<a href="https://www.youtube.com/watch?v=CubL463rhsQ" target="_blank">
    <img src="https://img.youtube.com/vi/CubL463rhsQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>173. Life Long Learning (6/7)</summary><br>

<a href="https://www.youtube.com/watch?v=D4aN7urRp3E" target="_blank">
    <img src="https://img.youtube.com/vi/D4aN7urRp3E/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>174. Life Long Learning (5/7)</summary><br>

<a href="https://www.youtube.com/watch?v=W37WANBMUTM" target="_blank">
    <img src="https://img.youtube.com/vi/W37WANBMUTM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>175. Life Long Learning (4/7)</summary><br>

<a href="https://www.youtube.com/watch?v=UgLx4rjcCO8" target="_blank">
    <img src="https://img.youtube.com/vi/UgLx4rjcCO8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>176. Life Long Learning (2/7)</summary><br>

<a href="https://www.youtube.com/watch?v=X7aWP6LngEs" target="_blank">
    <img src="https://img.youtube.com/vi/X7aWP6LngEs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>177. Life Long Learning (3/7)</summary><br>

<a href="https://www.youtube.com/watch?v=8uo3kJ509hA" target="_blank">
    <img src="https://img.youtube.com/vi/8uo3kJ509hA/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>178. Meta Learning – MAML (1/9)</summary><br>

<a href="https://www.youtube.com/watch?v=EkAqYbpCYAc" target="_blank">
    <img src="https://img.youtube.com/vi/EkAqYbpCYAc/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>179. Meta Learning – MAML (2/9)</summary><br>

<a href="https://www.youtube.com/watch?v=9k4ND-xjcgM" target="_blank">
    <img src="https://img.youtube.com/vi/9k4ND-xjcgM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>180. Meta Learning – MAML (3/9)</summary><br>

<a href="https://www.youtube.com/watch?v=PznN0w7dYc0" target="_blank">
    <img src="https://img.youtube.com/vi/PznN0w7dYc0/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>181. Meta Learning – MAML (4/9)</summary><br>

<a href="https://www.youtube.com/watch?v=knaAdp5uWRg" target="_blank">
    <img src="https://img.youtube.com/vi/knaAdp5uWRg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>182. Meta Learning – MAML (5/9)</summary><br>

<a href="https://www.youtube.com/watch?v=vUwOA3SNb_E" target="_blank">
    <img src="https://img.youtube.com/vi/vUwOA3SNb_E/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>183. Meta Learning – MAML (6/9)</summary><br>

<a href="https://www.youtube.com/watch?v=dV-Crj8hsJM" target="_blank">
    <img src="https://img.youtube.com/vi/dV-Crj8hsJM/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>184. Meta Learning – MAML (8/9)</summary><br>

<a href="https://www.youtube.com/watch?v=3z997JhL9Oo" target="_blank">
    <img src="https://img.youtube.com/vi/3z997JhL9Oo/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>185. Meta Learning – MAML (7/9)</summary><br>

<a href="https://www.youtube.com/watch?v=mxqzGwP_Qys" target="_blank">
    <img src="https://img.youtube.com/vi/mxqzGwP_Qys/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>186. Meta Learning – MAML (9/9)</summary><br>

<a href="https://www.youtube.com/watch?v=9jJe2AD35P8" target="_blank">
    <img src="https://img.youtube.com/vi/9jJe2AD35P8/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>187. Meta Learning - Gradient Descent as LSTM (1/3)</summary><br>

<a href="https://www.youtube.com/watch?v=NjZygLDXxjg" target="_blank">
    <img src="https://img.youtube.com/vi/NjZygLDXxjg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>188. Meta Learning - Gradient Descent as LSTM (2/3)</summary><br>

<a href="https://www.youtube.com/watch?v=G_xYYq772NQ" target="_blank">
    <img src="https://img.youtube.com/vi/G_xYYq772NQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>189. Meta Learning - Gradient Descent as LSTM (3/3)</summary><br>

<a href="https://www.youtube.com/watch?v=p0Tn8oZWZbQ" target="_blank">
    <img src="https://img.youtube.com/vi/p0Tn8oZWZbQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>190. Meta Learning – Metric-based (1/3)</summary><br>

<a href="https://www.youtube.com/watch?v=yyKaACh_j3M" target="_blank">
    <img src="https://img.youtube.com/vi/yyKaACh_j3M/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>191. Meta Learning – Metric-based (2/3)</summary><br>

<a href="https://www.youtube.com/watch?v=scK2EIT7klw" target="_blank">
    <img src="https://img.youtube.com/vi/scK2EIT7klw/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>192. Meta Learning – Metric-based (3/3)</summary><br>

<a href="https://www.youtube.com/watch?v=semSxPP2Yzg" target="_blank">
    <img src="https://img.youtube.com/vi/semSxPP2Yzg/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>193. More about Auto-encoder (2/4)</summary><br>

<a href="https://www.youtube.com/watch?v=hhsfEaVaeQU" target="_blank">
    <img src="https://img.youtube.com/vi/hhsfEaVaeQU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>194. More about Auto-encoder (3/4)</summary><br>

<a href="https://www.youtube.com/watch?v=ZRyoCBCFMOs" target="_blank">
    <img src="https://img.youtube.com/vi/ZRyoCBCFMOs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>195. More about Auto-encoder (4/4)</summary><br>

<a href="https://www.youtube.com/watch?v=DRLsw4CshqU" target="_blank">
    <img src="https://img.youtube.com/vi/DRLsw4CshqU/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>196. More about Auto-encoder (1/4)</summary><br>

<a href="https://www.youtube.com/watch?v=6ZWu4L7XOiQ" target="_blank">
    <img src="https://img.youtube.com/vi/6ZWu4L7XOiQ/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>197. Network Compression (1/6)</summary><br>

<a href="https://www.youtube.com/watch?v=dPp8rCAnU_A" target="_blank">
    <img src="https://img.youtube.com/vi/dPp8rCAnU_A/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>198. Network Compression (2/6)</summary><br>

<a href="https://www.youtube.com/watch?v=7B8Cx7woQk4" target="_blank">
    <img src="https://img.youtube.com/vi/7B8Cx7woQk4/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>199. Network Compression (3/6)</summary><br>

<a href="https://www.youtube.com/watch?v=mzZzn8fBvEs" target="_blank">
    <img src="https://img.youtube.com/vi/mzZzn8fBvEs/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>

<details>
<summary>200. Network Compression (4/6)</summary><br>

<a href="https://www.youtube.com/watch?v=fMsNf0ufYnY" target="_blank">
    <img src="https://img.youtube.com/vi/fMsNf0ufYnY/maxresdefault.jpg" 
        alt="[Youtube]" width="200">
</a>


</details>


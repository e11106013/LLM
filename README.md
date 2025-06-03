# LLM Knowledge Graph & RDF Processing Notebooks

本專案包含多個 Jupyter Notebook，展示如何運用大型語言模型（LLM）與 RDF 工具進行知識圖譜構建、道路路名 RDF 建模，以及本地化大型語言模型的測試。以下為各 Notebook 之簡介與用途。

---

## 1. LLM_to_Graph.ipynb
- https://github.com/e11106013/LLM/blob/main/LLM_to_Graph.ipynb

### 功能說明
- 利用 LLM（如 Llama、Groq API）從文章中自動抽取本體（ontology）與關係（relation），構建知識圖譜（Knowledge Graph）。
- 支援中文文本，並將段落切分、分詞、呼叫 LLM 產生三元組 (node_1, edge, node_2)。
- 以 NetworkX 及 PyVis 進行視覺化、社群偵測與顏色分群。
- 範例文件：以「賽德克．巴萊」霧社事件文章做知識圖譜生成。
  
### 主要套件
- langchain_community
- jq
- pyvis
- openai (Groq API)
- pandas, numpy, networkx, seaborn, matplotlib

### 用法
1. 安裝環境與下載 JSON 檔案。
2. 執行 Notebook 依序載入與處理數據，產生知識圖譜。
3. 可互動式瀏覽圖譜社群結構。

---

## 2. RDF_交通部_道路路名表_總表.ipynb
- https://github.com/e11106013/LLM/blob/main/RDF_交通部_道路路名表_總表.ipynb

### 功能說明
- 下載交通部公開「道路路名表-總表」Excel 檔案，轉換資料為 RDF 格式。
- 使用 rdflib 建立 RDF Graph，並以 Turtle、RDF/XML 格式存檔。
- 演示 SPARQL 查詢：如查詢所有道路名稱、查詢特定縣市道路名稱及長度。

### 主要套件
- pandas
- rdflib

### 用法
1. 下載官方 Excel 路名表。
2. 依 Notebook 步驟轉為 RDF，並可進行 SPARQL 查詢。
3. 輸出為 turtle (`.ttl`) 檔，或 RDF/XML 格式。

---

## 3. Testing_royal_ZhTW_ID_q4_k_GGUF.ipynb
- https://github.com/e11106013/LLM/blob/main/Testing_royal_ZhTW_ID_q4_k_GGUF.ipynb

### 功能說明
- 示範如何在本地端安裝與測試 Hugging Face 上的 GGUF 格式中文/印尼文 LLM（如 royal-ZhTW-ID）。
- 使用 llama-cpp-python 載入本地模型，並進行 prompt 測試（如翻譯、問答）。
- 支援 Hugging Face CLI 下載模型與登入。

### 主要套件
- llama-cpp-python
- huggingface_hub

### 用法
1. 安裝 llama-cpp-python。
2. Hugging Face CLI 登入並下載模型。
3. 載入模型後可直接以 Python 進行 prompt 測試。

---

## 環境建議

建議使用 Python 3.8 以上、Jupyter Lab/Notebook 執行。部分 Notebook 需配合 Google Colab 或 GPU 執行以加速 LLM 推論。

## 資料來源
- [檔案管理局](https://www.archives.gov.tw/).
- [交通部開放資料平台](https://link.motc.gov.tw/DownloadFile)
- [Hugging Face](https://huggingface.co/roylin1003/royal-ZhTW-ID-q4_k_m)
- Groq API、OpenAI API

## 聯絡與貢獻

如有問題或建議，歡迎於本 repo 提出 Issue 或 Pull Request。

---



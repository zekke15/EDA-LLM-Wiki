# EDA LLM Wiki — IC 設計中的 EDA 是什麼？

使用 EDA 官方技術文件建立可檢索的 Wiki 知識庫，並搭配 LLM 製作初學者 HTML 教學簡報。

## 六個 Wiki 主題
W01 EDA 入門；W02 RTL 與 Verilog；W03 Logic Synthesis；W04 Placement；W05 Routing；W06 Verification。

## 技術
Google Colab、Python、TF-IDF、Query Expansion、主題加權檢索、aisuite / Groq、HTML/CSS/JavaScript。

## 流程
官方文件 → 內容下載與檢查 → 切分 / TF-IDF Ingest → Query Expansion → V3 主題加權檢索 → LLM 生成 → 來源標記及結構檢查（最多重試三次）→ HTML 簡報 → 人工檢查。

詳見 [Workflow 與測試紀錄](docs/workflow.md)。

## 來源
- [OpenROAD](https://openroad.readthedocs.io/en/latest/)
- [Yosys](https://yosyshq.readthedocs.io/projects/yosys/en/stable/)
- [OpenLane 2](https://openlane2.readthedocs.io/en/stable/)

## 發布狀態
Colab 已產生八頁 HTML，但尚待上傳真正的 `index.html`、`wiki/` 文件與測試日誌到這個 Repo，網站尚未驗證。禁止提交 API Key、Secrets 或包含金鑰的 Notebook。

**檢索來源編號與輸出長度檢查，不代表技術事實已通過人工核對。**

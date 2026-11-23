# LLM Wiki Workflow 與反思

## Graph
```text
EDA 官方文件 W01–W06
  ↓ 下載/初步檢查
文字切分 + TF-IDF 索引 (ingest)
  ↓
提問 → Query Expansion → V3 主題加權檢索
  ↓ Wiki 段落 / 來源 ID
LLM 產生教材
  ↓
來源標記、輸出長度檢查
  ├─ FAIL → 重新生成（最多三次，否則標記未通過）
  └─ PASS → HTML 簡報 → 人工內容及操作驗證
```

## 實際執行與改善紀錄
原始檢索的首筆結果：EDA→W06，RTL→W02，Synthesis→W03，Placement/Routing→W01，Verification→W01。

加入 Query Expansion 後：EDA→W01，RTL→W02，Synthesis→W03，Placement/Routing→W01，Verification→W01。

加入主題加權 V3 後，前三筆來源：
- EDA：W01/W01/W01
- RTL/Verilog：W02/W02/W02
- Logic Synthesis：W03/W03/W03
- Placement/Routing：W05/W04/W04
- Verification：W06/W01/W06

## 反思
問題主要集中在檢索節點：中文提問對英文官方技術文件的匹配不穩。將檢查往前移至 LLM 生成之前，增加英文關鍵字擴充與文件主題加權，改善了預期來源排序。

V3 的來源匹配改善不等同於事實驗證。生成檢查的重試數與成果，需以 Colab 真正產生的 generation_log.json 為準，不能憑空填入。

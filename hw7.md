---

## 資料流程圖 - 描述版本

### 主要元件
1. **外部實體：Student User**
   - 提交填充題或開放性問答題的答案。
2. **核心處理：AI Grading System**
   - 系統主要處理流程：
     - **Answer Analysis**：分析提交的答案是否正確。
     - **Score Calculation**：根據答案計算得分。
     - **Result Storage and Feedback**：存儲結果並生成成績報告。
3. **外部實體：Teacher User**
   - 提供手動調整分數與審核功能。

### 資料存儲
- **Answer Database**：存儲學生提交的答案。
- **Results Database**：保存分析結果與生成的分數。

---

## 資料流程 - 文字流程

1. **Student User 提交答案**：
   - 學生將填充題或問答題答案提交至 AI Grading System。

2. **AI Grading System 處理**：
   - **Answer Analysis**：檢查答案，進行語義比對與正確性判定。
   - **Score Calculation**：根據答案正確性與分數規則計算成績。
   - **Result Storage and Feedback**：將成績存入 Results Database，並生成回饋。

3. **Teacher User 干預（如需）**：
   - 若有特殊或爭議性答案，系統通知教師進行手動檢查與分數調整。

4. **報告生成與回饋**：
   - 成績報告生成後提供給學生和教師檢視。

---

## 系統流程 - 模擬文字框架

```plaintext
External Entity: Student User
|
|--> [Submit Answers] --> Process: AI Grading System
                              |
                              |--> Subprocess: Answer Analysis
                              |
                              |--> Subprocess: Score Calculation
                              |
                              |--> Subprocess: Result Storage and Feedback
                              |
Results Feedback <-- [Results Database] <--|
                                            |
External Entity: Teacher User (Optional Adjustments)
```

---

# 你是用戶端，要連到公司 SVN Server 上新建資料夾
### 在 Repository Browser 中選擇位置 → 右鍵新增資料夾 就可以了
在 SVN（Subversion） 中，專案的儲存庫（repository）通常會採用一種標準目錄結構：

```bash
/projectname
├── trunk         ← 主線開發版本
├── branches      ← 分支開發區（例如測試版、試驗功能）
└── tags          ← 版本快照（如 v1.0、v2.0）
```

### 你在建立儲存庫時，沒有自動建立 trunk、branches、tags
那你需要自行建立  
且   以後Checkout 的位置應該是從 trunk

---
### 若有個  已存在的專案 要放進這個儲存庫
就複製整個專案進  trunk目錄

#### 步驟一：加入所有檔案

1. 開啟 `trunk` 資料夾
2. 按 `Ctrl + A` 全選（或你只選專案資料夾和 .sln）
3. 右鍵 → `TortoiseSVN` → `Add`


#### 步驟二：提交到 SVN 儲存庫

1. 加完後，再次 **右鍵空白處** → `SVN Commit`

2. 填寫 Commit 訊息，例如：

   ```
   Initial import of VS2019 C# project
   ```

3. 按 OK → 成功！


#### 🧼 建議忽略這些 VS 暫存檔案：

你可以在 `Add` 之前或 Commit 前忽略這些不需要版本控制的東西：

| 檔案/資料夾   | 說明                  |
| -------- | ------------------- |
| `.vs/`   | Visual Studio 暫存資料夾 |
| `bin/`   | 編譯輸出                |
| `obj/`   | 中繼檔                 |
| `*.user` | 開發人員個人設定檔，不建議版本控制   |

---

#### 🛠 忽略方式（Add to ignore list）：

1. 找到你不想加入的資料夾（如 `bin`）
2. 右鍵該資料夾 → `TortoiseSVN` → `Add to ignore list` → 選 `bin`
3. 系統會自動略過它，不會納入版本控制





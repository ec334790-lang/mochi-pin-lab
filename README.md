# Mochi 腳位實驗室

ESP32-C3 SuperMini 的腳位互動學習網站，以 Clawd Mochi 的螢幕接線當練習題。

- **腳位圖**：點任何一根腳，看它的功能、注意事項，以及 Mochi 的哪些功能會用到它
- **接線模擬**：把螢幕的 8 條線接到板子上再通電。接錯會跳出視窗指出哪裡要改；接對了 Mochi 會開機，可以用模擬的控制器切換 5 個功能（一般眼睛、瞇眼、終端機、畫布、Logo 動畫）
- **空間預算**：勾選要編進韌體的功能，看 Flash 和 RAM 的佔比

整個網站只有一個 `index.html`，不需要安裝或建置。

## 在自己電腦上看

直接用瀏覽器打開 `index.html`。

## 放上 GitHub Pages

1. 在 GitHub 建一個新的 repository（例如 `mochi-pin-lab`），設為 Public。
2. 把這個資料夾裡的 `index.html`、`README.md`、`.nojekyll` 上傳到 repository 的根目錄。
   - 網頁操作：Add file → Upload files → 拖進去 → Commit changes
   - 或用指令：
     ```
     git init
     git add .
     git commit -m "Mochi 腳位實驗室"
     git branch -M main
     git remote add origin https://github.com/<你的帳號>/mochi-pin-lab.git
     git push -u origin main
     ```
3. 到 repository 的 Settings → Pages，Source 選 **Deploy from a branch**，Branch 選 **main**、資料夾選 **/(root)**，按 Save。
4. 等一兩分鐘，網址會是 `https://<你的帳號>.github.io/mochi-pin-lab/`。

## 資料說明

- 排線、功能和程式片段取自 [Clawd Mochi](https://github.com/yousifamanuel/clawd-mochi) 開源專案（MIT 授權，作者 Yousuf Amanuel）：MOSI 10、SCK 8、RST 2、DC 1、CS 4、BL 3。
- 空間預算的數字是把 Clawd Mochi 原始碼用 arduino-esp32 3.3.0 編譯給 ESP32-C3（USB CDC On Boot 開啟）實際量出來的。5 個功能的 32 種勾選組合各編譯一次；完整韌體是 1,067,586 位元組（預設分割表的 81%），全域變數 37,152 位元組。不同版本的核心或函式庫會有幾 KB 的差異。
- 模擬螢幕上的眼睛和 logo 動畫是示意造型，實機會畫專案自己的圖案。
- 腳位左右排列依常見的 SuperMini 版型繪製，接線前請以板子上印的編號為準。

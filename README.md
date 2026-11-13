# Mochi 腳位實驗室

ESP32-C3 SuperMini 的腳位互動學習網站，以 Clawd Mochi 的螢幕接線當練習題。

- **課程**：8 堂課，每課有說明、任務和測驗
- **腳位圖**：點任何一根腳看功能與注意事項
- **接線模擬**：拉線、通電、按按鈕換顏文字，接錯會顯示對應症狀
- **空間預算**：試算 Flash 與 RAM 用量（分割表、WiFi/BLE、圖片、中文字型）

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

- Mochi 排線採用 Clawd Mochi 專案公開的接法：MOSI 10、SCK 8、RES 2、DC 1、CS 4、BL 3。
- 腳位左右排列依常見的 SuperMini 版型繪製，接線前請以板子上印的編號為準。
- 空間預算裡，「核心 + GFX + 螢幕驅動」與 RAM 靜態用量是實際編譯的數字；WiFi、BLE、網頁伺服器是估算值。
- 學習進度存在瀏覽器的 localStorage，不會上傳。

如何使用 Manus AI 串接 GitHub，將專案部署到 Cloudflare Pages？

本文將逐步帶你實作，從 Manus AI 出發，把專案自動上傳到 GitHub，最後部署到 Cloudflare Pages。過程中也會分享實際踩雷經驗，幫助你避免重複犯錯。

⸻

📦 前置準備
	1.	建立 Manus AI 帳號
	•	Manus 官網 註冊帳號
	•	確認你的帳號積分（Manus 採用積分制，一次操作會消耗額度）
	2.	GitHub Repository
	•	在 GitHub 建立一個新的 repo（公開或私有皆可）
	•	建議 repo 名稱與專案相關，例如：Artgo
	3.	Cloudflare 帳號
	•	前往 Cloudflare Pages
	•	確保你已經完成帳號註冊，並能夠新增專案

⸻

🚀 實作步驟

Step 1：將專案交給 Manus AI

在 Manus 對話框輸入指令（提示詞）：

請幫我到這個網址下載 index.html 檔案，部署到 GitHub 上，並協助我將此專案部署到 Cloudflare Pages。
專案名稱：Artgo

⚠️ 注意：建議一次只做一個動作（例如先上傳檔案到 GitHub，再進行部署），避免 AI 鬼打牆。

⸻

Step 2：GitHub 上傳驗證
	1.	確認 Manus 是否成功建立 repo 並上傳檔案。
	2.	若頁面顯示錯誤，建議：
	•	手動進入 GitHub repo → 檢查 index.html 是否存在
	•	若缺失，直接 手動上傳或覆蓋檔案

⸻

Step 3：連接 Cloudflare Pages
	1.	進入 Cloudflare Pages → Create a Project
	2.	選擇 Connect to GitHub → 授權 Cloudflare 存取該 repo
	3.	在設定畫面輸入：
	•	Branch：預設 main
	•	Build command：可留空（靜態 HTML 不需要）
	•	Output directory：/
	4.	點擊 Deploy，Cloudflare 會自動建置並分配一個網址，例如：

https://artgo.pages.dev


⸻

🧑‍💻 常見問題 & 踩雷記錄
	•	積分消耗過快：Manus 採積分制，若 AI 進入無限循環（鬼打牆），可能會短時間耗盡配額。
	•	檔案未正確上傳：即使 Manus 顯示「完成」，也要進 GitHub repo 確認 index.html 是否存在且內容正確。
	•	Cloudflare 頁面顯示錯誤：
	•	檢查 Branch 是否正確
	•	清除快取，避免舊版檔案殘留
	•	注意大小寫（例如 Index.html 與 index.html 是不同檔案）

⸻

✅ 建議做法
	1.	拆解任務：先請 Manus 上傳檔案，再進行 Cloudflare 部署，不要一次交代多件事。
	2.	手動驗證：AI 執行後一定要人工檢查 GitHub 與 Cloudflare 結果。
	3.	設停損點：若 AI 超過 10 分鐘仍無法完成，請立即中止，避免額外積分浪費。
	4.	備份檔案：建議保留本地副本，避免檔案被錯誤覆蓋。

⸻

🎯 結論

使用 Manus AI 串接 GitHub 並部署到 Cloudflare Pages 是可行的，但：
	•	指令需簡單、拆分
	•	驗證流程必不可少
	•	停損機制能避免時間與積分的浪費

完整紀錄與 36 張截圖已整理在案例頁面：
👉 AI 建站實作案例｜Manus AI × GitHub × Cloudflare

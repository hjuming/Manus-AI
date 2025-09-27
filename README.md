這份教學文件將引導你如何將 GitHub 上的專案部署到 Cloudflare Pages。

教學目標

本文件旨在引導使用者完成 GitHub 與 Cloudflare Pages 的串接與專案部署，讓你學會如何透過 Cloudflare Pages 快速、安全地託管你的靜態網站。

事前準備

在開始之前，請確保你已具備以下條件：

一個 GitHub 帳戶：並且你想要部署的專案已經推送到一個 GitHub Repository (儲存庫)。

一個 Cloudflare 帳戶：如果沒有，可以免費註冊。

部署教學：從 GitHub 到 Cloudflare Pages
步驟一：登入 Cloudflare 並找到 Pages 功能

前往 Cloudflare 儀表板 並登入你的帳戶。

在右側的導覽列中，點擊 Workers & Pages。

步驟二：建立新的 Pages 專案並連結 GitHub

進入 Workers & Pages 頁面後，點擊 Create application (建立應用程式)。

在建立頁面中，選擇 Pages 分頁。

點擊 Connect to Git (連接到 Git) 按鈕，以開始串接你的版本控制服務。

步驟三：授權 Cloudflare 存取你的 GitHub 帳戶

系統會引導你至 GitHub 授權頁面。如果你是第一次使用，GitHub 會請求你授權 Cloudflare Pages 存取你的儲存庫。

你可以選擇授權存取 所有儲存庫 (All repositories) 或 僅選擇特定儲存庫 (Only select repositories)。為了安全起見，建議選擇後者，並勾選你想要部署的專案。

點擊 Install & Authorize (安裝並授權)。

步驟四：選擇要部署的專案儲存庫

授權完成後，頁面會返回 Cloudflare。

此時，你應該能看到你的 GitHub 帳戶已成功連結。

在儲存庫列表中，找到並點選你想要部署的專案，然後點擊 Begin setup (開始設定)。

步驟五：設定建置與部署選項

這是整個流程中最關鍵的步驟，你需要告訴 Cloudflare Pages 如何建置 (Build) 你的專案。

Project name (專案名稱)：Cloudflare 會預設使用你的儲存庫名稱，你可以自行修改。這將會是你預設網址的一部分 (<專案名稱>.pages.dev)。

Production branch (生產分支)：選擇你的主要分支，通常是 main 或 master。當這個分支有新的 commit (提交) 時，Cloudflare Pages 會自動重新部署。

Build settings (建置設定)：

Framework preset (框架預設集)：Cloudflare Pages 能自動偵測許多常見的前端框架 (如 React, Vue, Hugo 等)。如果你的專案是使用這些框架，直接選取它，Cloudflare 會自動填入下方的建置指令和輸出目錄。

Build command (建置指令)：如果你的專案需要編譯 (例如：使用 Vite, Webpack 或需要處理 Sass/TypeScript)，請在此填寫建置指令。

範例 (React/Vite): npm run build

範例 (純 HTML/CSS/JS): 如果你的專案是純靜態檔案，此欄位可以留空。

Build output directory (建置輸出目錄)：這是執行建置指令後，最終要部署的靜態檔案所在的資料夾。

範例 (React/Vite): dist 或 build

範例 (純 HTML/CSS/JS): 如果你的專案根目錄就是網站內容，請填寫 / 或 .。

(選用) Environment variables (環境變數)：如果你的專案需要使用 API 金鑰等機敏資訊，可以在這裡設定。

確認所有設定後，點擊 Save and Deploy (儲存並部署)。

步驟六：等待部署完成

點擊儲存後，Cloudflare Pages 會開始從 GitHub 拉取你的程式碼，並執行你設定的建置指令。

你可以看到詳細的部署日誌 (Deployment logs)，方便排查問題。

首次部署通常需要幾分鐘時間。當狀態顯示 Success 時，代表你的網站已成功上線！

Cloudflare 會提供一個 .pages.dev 的專屬網域給你，點擊該網址即可預覽你的網站。

結論

恭喜你！你已經成功地將 GitHub 專案部署到 Cloudflare Pages 上。

從現在起，每當你將新的變更 push 到你設定的生產分支 (main 或 master) 時，Cloudflare Pages 都會自動觸發新的建置與部署，實現了 CI/CD (持續整合/持續部署) 的自动化流程，讓你的網站維護更加輕鬆。

如果你需要綁定自己的域名，可以到專案的 Custom domains 分頁進行設定。

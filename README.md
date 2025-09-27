# 🚀 手把手教學：將你的 GitHub 專案部署到 Cloudflare Pages！

嗨！這份教學文件將會像你的專屬嚮導，一步步帶你將存放在 GitHub 上的專案，免費、快速地部署到 Cloudflare Pages，讓全世界都能看見你的作品。準備好了嗎？我們開始吧！

---

## 📋 **第一站：行前準備與確認**

在我們踏上這趟旅程之前，請先確認你的背包裡有這兩樣東西：

* **一個 GitHub 帳戶**：並且你想要部署的專案程式碼，已經好好地放在一個 GitHub 儲存庫 (Repository) 裡了。
* **一個 Cloudflare 帳戶**：如果還沒有，別擔心，可以到 [官網](https://dash.cloudflare.com/sign-up) 註冊一個，過程完全免費！

---

## 🗺️ **第二站：串接 GitHub 與 Cloudflare Pages**

現在，我們要來搭起 GitHub 和 Cloudflare 之間的橋樑。

### **1. 登入 Cloudflare 尋找 Pages 入口**

* 首先，請前往 **[Cloudflare 儀表板](https://dash.cloudflare.com/)** 並登入你的帳戶。
* 在左側的導覽列中，找到並點擊 **<span style="color: #f0ad4e;">Workers & Pages</span>** 的選項。

### **2. 建立新專案，連接到 Git**

* 進入 Workers & Pages 頁面後，你會看到一個大大的按鈕，點擊 **<span style="color: #5cb85c;">Create application</span>** (建立應用程式)。
* 接著，在上方選擇 **Pages** 分頁，然後點擊 **<span style="color: #5bc0de;">Connect to Git</span>** (連接到 Git)。

### **3. 授權 Cloudflare 存取 GitHub**

* 點擊後，畫面會跳轉到 GitHub，這是為了請求你的授權。
* GitHub 會詢問你，是否同意讓 Cloudflare Pages 存取你的儲存庫。這裡你有兩個選擇：
    * `All repositories` (所有儲存庫)
    * `Only select repositories` (僅選擇特定儲存庫)
* **<span style="color: #d9534f;">強烈建議</span>** 選擇 **`Only select repositories`**，然後勾選你這次**<span style="color: #d9534f;">真正要部署的那個專案</span>**。這是一個比較安全的做法！
* 按下 **Install & Authorize** (安裝並授權)，給予通行許可。

---

## ⚙️ **第三站：設定專案的建置與部署**

這是整趟旅程的**<span style="color: #d9534f;">核心環節</span>**！我們需要告訴 Cloudflare 如何「組裝」你的專案，讓它變成一個可以運行的網站。

### **1. 專案基本設定**

* **Project name (專案名稱)**：為你的網站取個名字吧！它將成為你預設網址的一部分，例如：`my-awesome-project.pages.dev`。
* **Production branch (生產分支)**：選擇你的主要程式碼分支，通常是 `main` 或 `master`。**<span style="color: #5bc0de;">這非常重要</span>**，因為未來只要這個分支有任何更新，Cloudflare 就會自動幫你重新部署網站！

### **2. Build settings (建置設定)**

* **Framework preset (框架預設集)**：
    * Cloudflare 非常聰明，它認識很多主流的前端框架 (例如 React, Vue, Svelte, Vite, Hugo 等)。
    * 如果你的專案是使用這些框架，直接在下拉選單中選擇它。Cloudflare 會像魔法一樣，**<span style="color: #5cb85c;">自動填寫</span>** 下方的建置指令和輸出目錄！
* **Build command (建置指令)**：
    * 這個指令是告訴 Cloudflare：「嘿，請用這個指令來打包我的專案」。
    * 如果你的專案是使用 Vite 或 Create React App，指令通常是 `npm run build`。
    * **<span style="color: #f0ad4e;">特別注意</span>**：如果你的專案只是單純的 **HTML, CSS, JavaScript 靜態檔案**，完全不需要任何編譯或打包，那**<span style="color: #f0ad4e;">這個欄位請留空</span>**！
* **Build output directory (建置輸出目錄)**：
    * 執行完「建置指令」後，所有打包好的、最終要上傳的網站檔案都會放在這個資料夾。
    * 常見的名稱有 `dist` (Vite 專案)、`build` (Create React App 專案) 或 `public` (Hugo 專案)。
    * 如果你的專案是純靜態檔案，根目錄就是網站內容，可以直接填寫 **<span style="color: #f0ad4e;">`/`</span>**。

### **3. 儲存並部署**

* 確認所有設定都無誤後，勇敢地按下 **<span style="color: #5cb85c;">Save and Deploy</span>** (儲存並部署)！

---

## 🎉 **終點站：部署成功！**

* 點擊部署後，你會看到一個充滿程式碼的日誌畫面。這是 Cloudflare 正在幕後辛勤工作的過程：從 GitHub 拉取你的程式碼 -> 安裝相依套件 -> 執行建置指令 -> 部署到全球網路上。
* 請耐心等待幾分鐘，當你看到狀態顯示為 **<span style="color: #5cb85c;">Success</span>** (成功) 時，就代表……

**<span style="color: #d9534f; font-size: 1.2em;">恭喜你！你的網站已經成功上線了！</span>**

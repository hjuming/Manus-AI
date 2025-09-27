# 如何使用 Manus AI 串接 GitHub，將專案部署到 Cloudflare Pages？

本文將逐步帶你實作，從 Manus AI 出發，把專案自動上傳到 GitHub，最後部署到 Cloudflare Pages。過程中也會分享實際踩雷經驗，幫助你避免重複犯錯。

---

## 📦 前置準備

1. **建立 Manus AI 帳號**
   - [Manus 官網](https://manus.im) 註冊帳號
   - 確認帳號積分（Manus 採積分制，一次操作會消耗額度）

2. **GitHub Repository**
   - 在 [GitHub](https://github.com) 建立一個新的 repo（公開或私有皆可）
   - 建議 repo 名稱與專案相關，例如：`Artgo`

3. **Cloudflare 帳號**
   - 前往 [Cloudflare Pages](https://pages.cloudflare.com/)
   - 確保能夠新增專案

---

## 🚀 實作步驟

### Step 1：將專案交給 Manus AI
在 Manus 對話框輸入指令（提示詞）：

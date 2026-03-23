# 📖 daily-wird

This n8n workflow handles the daily Quran wird by sending 2 Quran pages to a Telegram channel using a chat bot.

---

## 🤖 What This Workflow Does:

* **Data Table:** Acts as a memory to save the last Quran page sent.
* **Telegram:** Sends daily Quran wird to a Telegram Channel.

---

## ⚙️ How To Set This Up:

### 📥 After You Import the JSON File to Your n8n:

#### 1. Schedule Trigger
Change the date and time to a suitable one.
> **Note:** Defaults to daily at 8 am.

#### 2. Create an n8n Data Table
Create a native n8n table with the following:
* **Column:** Named `PageNumber` (Number type).
* **Initial Row:** Add one row that starts with `0`.

#### 3. Telegram Bot Credentials
Add your Telegram chat bot credentials to n8n using the official documentation:
👉 [n8n Telegram Setup Guide](https://docs.n8n.io/integrations/builtin/credentials/telegram/#using-api-bot-access-token)

#### 4. Get Channel ID
Add your bot to your target Telegram channel as an Administrator and retrieve the **Channel ID**.

#### 5. Finalize Node Settings
* Apply the created **Credentials** to the Telegram Node.
* Paste your **Channel ID** into the Chat ID field of the Telegram Node.

---

### 🛠️ Technical Details
* **Logic:** Includes a JavaScript reset to wrap from page 604 back to page 1.
* **Source:** Images are pulled dynamically from the `QuranHub` GitHub repository.

# daily-news-to-script-emailer-n8n
 Fetch daily news on any topic, convert it to an AI-generated video script, and send it to Gmail every morning — fully automated with n8n.
# 📰 Daily Topic-Based News to Script & Email Automation (n8n)

This n8n workflow automatically fetches the latest news articles for a chosen topic (e.g., **sports**, **AI**, **finance**, etc.), uses an AI model to turn that news into a 60-second video script, and emails it to a chosen Gmail address every morning at 8 AM.

---

## 🔁 Workflow Summary

| Feature | Description |
|--------|-------------|
| ⏰ Trigger | Scheduled daily at 8:00 AM |
| 🧠 Input | Topic (e.g., "sports") |
| 🌐 News API | [NewsData.io](https://newsdata.io) |
| 🤖 Script Generation | [OpenRouter Mistral 7B](https://openrouter.ai) |
| 📧 Output | Email with AI-generated script |

---

## 📌 Use Case

Perfect for:
- Daily content creators
- Newsletter writers
- YouTubers or Reels creators who want a fast script every day
- Automation enthusiasts

---

## 🧩 Node Breakdown

1. **Schedule Trigger**
   - Triggers every day at 8 AM.

2. **Edit Fields (Set Topic)**
   - Assigns the topic for the day (e.g., `sports`).

3. **HTTP Request1**
   - Calls the NewsData.io API to fetch top articles.

4. **Code Node**
   - Formats news titles and links into a string for scripting.

5. **HTTP Request (Script Generator)**
   - Sends the news string to OpenRouter Mistral 7B to generate a 60-second script.

6. **Edit Fields1**
   - Cleans up the AI response.

7. **Gmail Node**
   - Sends the final script to your Gmail inbox.

---

## 📥 Files in This Repo

| File | Description |
|------|-------------|
| `daily-news-to-script-emailer-n8n.json` | Full n8n workflow export |
| `README.md` | This documentation |

---

## 🛠️ Setup Instructions

1. **Import the JSON Workflow in n8n**
2. Set your credentials:
   - **Gmail OAuth2** (Add your Gmail account)
   - Replace `Bearer sk-...` with your **OpenRouter API key**
   - Replace `apikey=...` in NewsData API with your own API key
3. (Optional) Change the topic in the **"Edit Fields"** node
4. Enable workflow

---

## 🔐 Environment Variables & Credentials

| API | Required | Where to Set |
|-----|----------|--------------|
| OpenRouter API | ✅ | HTTP Request header |
| NewsData.io API | ✅ | In the request URL |
| Gmail OAuth2 | ✅ | Connect under "Gmail" node credentials |

---

## 📸 Workflow Screenshot

> _(Add a screenshot of your workflow here for better presentation)_  
> Example:  
> ![Workflow Screenshot](./screenshot.png)

---

## 🧠 Credits

Built by **Vishnu Marella Pavan Kumar** using [n8n](https://n8n.io), OpenRouter.ai, and NewsData.io.

---

## 📝 License

This project is licensed under the MIT License. Feel free to modify, improve, and share!


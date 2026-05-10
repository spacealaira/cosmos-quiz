[README.md](https://github.com/user-attachments/files/27389612/README.md)
# 🪐 Cosmos Quiz



A fully interactive, space-themed educational quiz game built with vanilla HTML/CSS/JavaScript, powered by a real-time global leaderboard.

**🌐 Live site:** [spacealaira.github.io/cosmos-quiz](https://spacealaira.github.io/cosmos-quiz/)

## 🚀 Origin Story

Built in a single afternoon as a live educational tool 
for a real event. Went from zero to deployed full-stack 
app - frontend, database, and live leaderboard - while 
the session was being planned. The constraints were real: 
no prep time, real users, had to work first try.

---

## ✨ Features

- **10 space & astronomy questions** with instant feedback and explanations
- **45-second countdown timer** per question — the bar changes colour as time runs out
- **Speed-based scoring** — the faster you answer, the more points you earn (up to 100 pts per question, 1000 pts total)
- **🔥 Streak tracker** — displays a live streak counter when you get consecutive correct answers
- **Global leaderboard** — scores are saved to a real database and ranked across all players in real time
- **Name entry screen** — every player registers before playing
- **Fully responsive** — works on desktop and mobile
- **Animated space theme** — twinkling stars, nebula glows, and a deep space colour palette

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | HTML, CSS, Vanilla JavaScript |
| Database | [Supabase](https://supabase.com) (PostgreSQL) |
| Hosting | GitHub Pages |
| Fonts | Google Fonts (Orbitron, Nunito) |

---

## 🗄️ Database Schema

```sql
create table scores (
  id bigint generated always as identity primary key,
  name text not null,
  score int not null,
  total int not null,
  pct int not null,
  correct int,
  timeouts int,
  created_at timestamptz default now()
);
```

---

## 🚀 How to Run Locally

No build tools or dependencies needed — it's plain HTML.

1. Clone the repo:
   ```bash
   git clone https://github.com/spacealaira/cosmos-quiz.git
   ```
2. Open `index.html` in your browser.

> Note: The leaderboard requires an internet connection to reach Supabase.

---

## 📁 Project Structure

```
cosmos-quiz/
└── index.html    # Entire app — quiz logic, styling, and Supabase integration
```

---

## 🎮 How Scoring Works

Each question is worth up to **100 points**. Points are calculated based on how quickly you answer:

```
points = 10 + (seconds_remaining / 45) × 90
```

- Answer immediately → **100 pts**
- Answer with 1 second left → **~12 pts**
- Time out → **0 pts**

Maximum possible score: **1,000 points**

---

## 👩‍💻 Author

Built by **Alaira** — SDR at InfluxData, BSoftEng student at Carleton University.

---

## 📄 License

MIT — feel free to fork and build your own quiz!

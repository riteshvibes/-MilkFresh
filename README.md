# 🥛 MilkFresh — Milk Freshness Tester

A simple, modern web application to test milk freshness using pH, temperature, fat percentage, and lactometer readings. Built with **React + Vite** (frontend) and **Python Flask** (backend).

---

## 📁 Project Structure

```
milk-freshness-tester/
├── backend/
│   ├── app.py              # Flask API server
│   └── requirements.txt    # Python dependencies
├── frontend/
│   ├── src/
│   │   ├── components/     # Header, Footer
│   │   ├── pages/          # Home, TestMilk, About
│   │   ├── App.jsx         # Root component with routing
│   │   ├── App.css
│   │   ├── index.css       # Design system
│   │   └── main.jsx        # Entry point
│   ├── index.html
│   ├── package.json
│   └── vite.config.js
└── README.md
```

---

## 🚀 Quick Start (Local Development)

### Prerequisites
- **Node.js** 18+ and **npm**
- **Python** 3.9+

### 1. Start the Backend

```bash
cd backend
pip install -r requirements.txt
python app.py
```

The API will run at `http://localhost:5000`.

### 2. Start the Frontend

```bash
cd frontend
npm install
npm run dev
```

The app will open at `http://localhost:5173`.

> The frontend uses `http://localhost:5000` as the default API URL. You can override it by creating a `.env` file in `frontend/`:
> ```
> VITE_API_URL=http://localhost:5000
> ```

---

## 🧪 API Reference

### `POST /predict`

**Request body (JSON):**
```json
{
  "ph": 6.7,
  "temperature": 4,
  "fat": 4.0,
  "lactometer": 28
}
```

**Response:**
```json
{
  "freshness_score": 100,
  "status": "Fresh and Safe",
  "quality_grade": "A",
  "safety_message": "✅ This milk is fresh and safe to consume.",
  "color": "green",
  "shelf_life": "27 Hours Remaining",
  "details": {
    "ph_status": "Fresh and Safe",
    "temperature_status": "Good (Well Refrigerated)",
    "fat_status": "Normal",
    "lactometer_status": "Normal"
  }
}
```

---

## 🌐 Deployment

### Frontend → Vercel

1. Push your code to GitHub.
2. Import the repo on [vercel.com](https://vercel.com).
3. Set **Root Directory** to `frontend`.
4. Set environment variable: `VITE_API_URL` = your deployed backend URL.
5. Deploy!

### Backend → Render

1. Push your code to GitHub.
2. Create a new **Web Service** on [render.com](https://render.com).
3. Set **Root Directory** to `backend`.
4. **Build Command**: `pip install -r requirements.txt`
5. **Start Command**: `gunicorn app:app`
6. Deploy!

---

## 📊 Freshness Logic

| Score     | Grade | Status          |
|-----------|-------|-----------------|
| 85 – 100% | A     | Fresh and Safe  |
| 60 – 84%  | B     | Safe to Drink   |
| 40 – 59%  | C     | Near Spoilage   |
| 0 – 39%   | D     | Spoiled         |

---

## 🛠 Tech Stack

- **Frontend**: React 19, Vite, React Router, Vanilla CSS
- **Backend**: Python Flask, Flask-CORS, Gunicorn

---

Built with ❤️ for safe dairy consumption.

# 🎥 **CineMood AI**  
**AI-Powered Mood & History-Based Movie Recommender**  

> *“Because the right movie can change your mood—and your night.”*  

---

## 🔍 How It Works  

### 1. **💬 Conversational Input**  
- Chat naturally with the system:  
  - *“I’m feeling nostalgic”*  
  - *“Show me something thrilling but not too scary”*  
  - *“Feel-good movies for a rainy evening.”*  

### 2. **🤖 AI Multi-Agent Engine**  
- **Emotion Detection**: Identifies how you feel—or want to feel.  
- **Movie Metadata Analysis**: Understands genre, cast, themes, and more.  
- **Mood Matching**: Selects movies that align with your emotional state.  

### 3. **🎯 Smart Mood Precision**  
- Handles simple moods (*sad*, *happy*, *stressed*) and nuanced emotional requests (*uplifting but slow-paced*).  

---

## ✨ Why CineMood AI?  
- **Beyond Simple Genres**: Goes deeper than “action” or “romance” to match emotional tone.  
- **Perfect for Any Occasion**: Solo watch nights or group movie marathons.  
- **Adaptive Learning**: Improves accuracy as you give feedback.  

---

## 🧠 Dual-Model Recommendation System  

We combine **real-time mood detection** with **watch-history-based collaborative filtering** for richer recommendations.  

### **Model 1: Mood-Based Recommender**  
- Powered by **Gemini 2.0 Flash** and a **multi-agent AI pipeline**.  
- User’s mood or query is analyzed into an *emotional fingerprint*.  
- The fingerprint is vectorized and matched against a **LanceDB** database of pre-encoded movie embeddings.  
- A refinement layer evaluates extra factors (cast, themes, pacing) to balance accuracy with variety.  
- Composite scoring ranks final results by *emotional alignment + diversity*.  

---

### **Model 2: Watch History Recommender**  
- Built with **Cornac’s BiVAE** (Bilinear Variational Autoencoder).  
- Learns patterns from your ratings and viewing history.  
- Finds a “closest match” to similar users in the **MovieLens 32M dataset** (750k+ movies, 8M+ ratings).  
- Blends results with mood-based filtering to give **context-aware suggestions**.  

---

## 🎬 Playlist Personalization  
- Feedback from users dynamically updates weighting of recommendation factors.  
- Considers **Genre, Cast, Themes, Emotional Impact** from your history.  
- Generates evolving, highly personal playlists that reflect your tastes and current state of mind.  

---

## 🧰 Tech Stack  

| Layer         | Technology                |
| ------------- | ------------------------- |
| **Frontend**  | Next.js (TypeScript)      |
| **Backend**   | FastAPI (Python)          |
| **Database**  | Firebase                  |
| **Vector DB** | LanceDB                   |
| **AI Agents** | Gemini (gemini-2.0-flash) |
| **BiVAE**     | Cornac                     |

---

## ⚙️ Setup Instructions  

- Clone the repository:

```bash
    git clone https://github.com/AliAsgar-Maheshwarwala110/Cine-mood-AI.git
    cd cs671-hack
```

- Install dependencies:

```bash
    pip install -r requirements.txt
```

- Set up environment variables:

```bash
    cp .env.example .env
```

- BiVAE QuickStart and Testing:
   - 1. Train BiVAE
   ```bash
      cd BiVAE
      jupyter notebook cornac_bivae_deep_dive_50.ipynb
   ```
   - 2. Download links
      - [🔗 Model Weights](https://drive.google.com/file/d/1QsUqXv-Jk6EdgTiwkIWKvgZkBubb_LFP/view?usp=sharing)  
      - [📁 Dataset](https://drive.google.com/file/d/1S4MpwbRSsAcAas6IjlsT_pDYW3-0hKtE/view?usp=sharing)  
      - [📊 Training Data](https://drive.google.com/file/d/1ZH7Qnw37GcXgHUWiy8MT435kIy8bKFbj/view?usp=sharing)  
      - [💾 Auto-saved Outputs](https://drive.google.com/file/d/1Wz0lKvu0Sz9LS70bdVpny_W1uH3BTQC8/view?usp=sharing)



- cd into the `frontend` directory , install dependencies and start the frontend server:

```bash
    cd frontend
    npm install
    npm run dev
```

- cd into the `backend` directory and start the server:

```bash
    cd backend
    uvicorn main:app --reload --port 8000
```

- cd into the `BiVAE` directory and start the second server:
```bash
   cd backend
   uvicorn bivae_web2:app --reload --port 8001
   ngrok http 8001
```
---

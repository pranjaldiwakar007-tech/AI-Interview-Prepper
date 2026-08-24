
# 🧠 AI-Powered Technical Interview Prepper

A full-stack AI-powered application designed to simulate real-world technical interviews. Users can practice conceptual and coding questions through voice and code, receiving AI-driven feedback, technical scores, confidence scores, ideal answers, and detailed performance analytics.

### ✨ Key Features

### 🎯 Customizable Interviews
- Select interview roles such as **MERN Stack Developer, Python Developer, and Data Science**.
- Choose the **difficulty level** based on experience.
- Select between **conceptual oral interviews** and **coding-mix interviews**.

### 🔄 Hybrid Input System
- **🎙️ Voice Response:** Uses **OpenAI Whisper** to transcribe verbal answers for conceptual questions.
- **💻 Code Editor:** Integrated **Monaco Editor** for solving coding challenges directly in the browser.

### 🤖 AI-Powered Evaluation
- **Dynamic Question Generation:** Uses the **Google Gemini API** to generate unique, role-specific interview questions.
- **Smart Evaluation:** Evaluates verbal explanations and code submissions to generate:
  - Technical Score
  - Confidence Score
  - Personalized AI Feedback
  - Ideal Answer / Solution
- Includes validation for empty, irrelevant, nonsensical, or invalid responses.

### 📊 Detailed Performance Analytics
- Interview session history with overall performance scores.
- Per-question breakdown of user submissions and ideal answers.
- Interactive performance visualizations using **Chart.js**.

### 🔐 Secure Authentication
- JWT-based user registration and authentication.
- Password hashing using **bcryptjs**.

## 🛠️ Tech Stack

### Frontend
- **React (Vite)**
- **Redux Toolkit**
- **Tailwind CSS**
- **Monaco Editor**
- **Chart.js / React-Chartjs-2**
- **React Router DOM**

### Backend API Gateway
- **Node.js**
- **Express.js**
- **MongoDB**
- **Mongoose**
- **JWT**
- **bcryptjs**

### AI Microservice
- **Google Gemini API**
  
## 🚀 Getting Started

### Prerequisites

1. **Node.js** (v16+) and **npm**.
2. **Python** (v3.9+) and **pip**.
3. **MongoDB**: Local instance or Atlas URI.
4. **Google Gemini API Key**: Required for AI-powered question generation and evaluation.
5. **FFmpeg**: Required for audio processing and speech transcription.

### 1. Clone the Repository

```bash
git clone https://github.com/pranjaldiwakar007-tech/AI-Interview-Prepper.git
cd Ai-Interview-Prepper

```

### 2. Backend Setup (Node.js)

```bash
cd backend
npm install

# Create a .env file
echo "PORT=5000" > .env
echo "MONGO_URI=your_mongodb_connection_string" >> .env
echo "JWT_SECRET=your_jwt_secret" >> .env
echo "NODE_ENV=development" >> .env

# Run the server
npm run server

```
source venv/bin/activate  # On Windows: venv\Scripts\activate


# Create a .env file
AI_SERVICE_PORT=8000
GEMINI_API_KEY=your_gemini_api_key

# Run the microservice
uvicorn main:app --reload --port 8000

```

### 4. Frontend Setup (React)

```bash
cd ../frontend
npm install

# Create a .env file
echo "VITE_API_URL=http://localhost:5000/api" > .env

# Run the frontend
npm run dev

```
### or shortcut

```
CLICK ON FOR-FIRST-TIME.BAT FILE AND RUN

```
---


## Most important: Updated Architecture Overview

```md
## 📐 Architecture Overview

The application follows a microservices-inspired architecture that separates the user interface, core application logic, and AI processing.

### 1. Client — React Frontend
Handles:

- Interview configuration
- Audio recording
- Voice responses
- Monaco-based code editing
- Displaying AI feedback and scores
- Performance analytics

### 2. Node.js Server — API Gateway
Acts as the central backend layer and handles:

- User authentication and authorization
- JWT validation
- MongoDB data persistence
- Interview session management

### 4. Google Gemini API
Powers:

- Dynamic interview question generation
- Context-aware answer evaluation
- Code logic evaluation
- Personalized feedback
- Technical and confidence scoring
- Ideal answer generation

```
### Request Flow

```text
                    ┌─────────────────────┐
                    │   React Frontend    │
                    │ Voice + Code Input  │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │ Node.js / Express   │
                    │     API Gateway     │
                    └───────┬───────┬─────┘
                            │       │
                  Auth/Data │       │ AI Requests
                            ▼       ▼
                     ┌──────────┐  ┌──────────────────┐
                     │ MongoDB  │  │ GEMINI API │
                     └──────────┘  └───────┬──────────┘
                                           │
                              ┌────────────┴────────────┐
                              ▼                         ▼
                     ┌────────────────┐       ┌────────────────┐
                     │ Google Gemini  │        │
                     │ Generation +   │       │ Speech-to-Text │
                     │ Evaluation     │       │                │
                     └────────────────┘       └────────────────┘

```
## 🤝 Contributing

Contributions are welcome! Please fork the repository and submit a pull request.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

Distributed under the MIT License. See `LICENSE` for more information.
